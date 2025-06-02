<template>
    <div class="home-container">
      <!-- Caja del nombre de usuario y cerrar sesión en la parte superior derecha -->
      <div class="user-box" @click="toggleMenu">
        {{ usuario.nombre }}
        <div v-if="mostrarMenu" class="dropdown-menu">
          <button @click="cerrarSesion">Cerrar sesión</button>
        </div>
      </div>

      <!-- Título de la página de inicio -->
      <h1>Página de Inicio</h1>
    </div>
  </template>

  <script setup>
  import { ref, onMounted } from 'vue'
  import { useRouter } from 'vue-router'

  const router = useRouter()
  const mostrarMenu = ref(false)
  const usuario = ref({ nombre: '' })

  // Cargar usuario al inicio
  onMounted(() => {
    // Cargar el usuario actual desde localStorage
    const datosUsuario = localStorage.getItem('usuario')
    if (datosUsuario) {
      usuario.value = JSON.parse(datosUsuario)
    } else {
      router.push('/login') // Redirige si no hay sesión activa
    }
  })

  function toggleMenu () {
    mostrarMenu.value = !mostrarMenu.value
  }

  function cerrarSesion () {
    localStorage.removeItem('usuario') // Eliminar el usuario actual
    router.push('/login') // Redirige al login
  }
  </script>

  <style scoped>
  .home-container {
    position: relative;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    height: 100vh;
    font-size: 2rem;
    padding: 20px;
  }

  .user-box {
    position: absolute;
    top: 20px;
    right: 20px;
    background-color: #f0f0f0;
    padding: 10px 15px;
    border-radius: 8px;
    cursor: pointer;
    font-size: 14px;
    font-weight: bold;
    box-shadow: 0 2px 4px rgba(0,0,0,0.1);
  }

  .dropdown-menu {
    margin-top: 8px;
    background-color: white;
    border: 1px solid #ddd;
    border-radius: 6px;
    padding: 8px;
    position: absolute;
    right: 0;
    top: 100%;
    box-shadow: 0 2px 6px rgba(0,0,0,0.15);
  }

  .dropdown-menu button {
    background: none;
    border: none;
    padding: 5px 10px;
    cursor: pointer;
    font-weight: normal;
    color: #c62828;
  }

  .dropdown-menu button:hover {
    background-color: #f5f5f5;
  }

  h1 {
    text-align: center;
    margin-bottom: 20px;
  }
  </style>

<template>
  <div class="min-h-screen bg-gradient-to-br from-gray-50 to-gray-100 flex items-center justify-center px-4">
    <div class="max-w-md w-full space-y-8">
      <!-- Logo/Header -->
      <div class="text-center">
        <h1 class="text-4xl font-bold text-gray-800 mb-2">
          Bienvenido a 
        </h1>
        <p class="text-gray-600 text-lg">
          EDMODO
        </p>
      </div>

      <!-- Card principal -->
      <div class="bg-white rounded-2xl shadow-sm border border-gray-200 p-8 space-y-6">
        <!-- Descripción -->
        <div class="text-center">
          <p class="text-gray-600">
            Inicia sesión o crea una cuenta para comenzar
          </p>
        </div>

        <!-- Botones -->
        <div class="space-y-4">
          <!-- Botón de Login -->
          <NuxtLink 
            to="/Login.vue" 
            class="w-full bg-green-600 hover:bg-green-700 text-white font-medium py-3 px-4 rounded-lg transition duration-200 ease-in-out transform hover:scale-105 flex items-center justify-center"
          >
            <svg class="w-5 h-5 mr-2" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M11 16l-4-4m0 0l4-4m-4 4h14m-5 4v1a3 3 0 01-3 3H6a3 3 0 01-3-3V7a3 3 0 013-3h7a3 3 0 013 3v1"></path>
            </svg>
            Iniciar Sesión
          </NuxtLink>

          <!-- Botón de Registro -->
          <NuxtLink 
            to="http://localhost:3000/register" 
            class="w-full bg-white hover:bg-gray-50 text-green-600 font-medium py-3 px-4 rounded-lg border-2 border-green-600 transition duration-200 ease-in-out transform hover:scale-105 flex items-center justify-center"
          >
            <svg class="w-5 h-5 mr-2" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M18 9v3m0 0v3m0-3h3m-3 0h-3m-2-5a4 4 0 11-8 0 4 4 0 018 0zM3 20a6 6 0 0112 0v1H3v-1z"></path>
            </svg>
            Crear Cuenta
          </NuxtLink>
        </div>

        <!-- Divider opcional -->
        <div class="relative">
          <div class="absolute inset-0 flex items-center">
            <div class="w-full border-t border-gray-200"></div>
          </div>
          <div class="relative flex justify-center text-sm">
            <span class="px-2 bg-white text-gray-500">¿Primera vez aquí?</span>
          </div>
        </div>

        <!-- Información adicional -->
        <div class="text-center">
          <p class="text-sm text-gray-500">
            Al continuar, aceptas nuestros términos y condiciones
          </p>
        </div>
      </div>

      <!-- Footer opcional -->
      <div class="text-center">
        <p class="text-sm text-gray-400">
          © 2025 EDMODO. Todos los derechos reservados.
        </p>
      </div>
    </div>
  </div>
</template>

<script lang="ts" setup>
// Meta tags para SEO
useHead({
  title: 'Bienvenido - Tu Aplicación',
  meta: [
    { name: 'description', content: 'Página de inicio - Inicia sesión o regístrate' }
  ]
})

// Opcional: Redireccionar si ya está autenticado
// onMounted(() => {
//   // Aquí puedes agregar lógica para verificar si el usuario ya está logueado
//   // y redirigirlo a la página principal de la app
// })
</script>

<style scoped>
/* Estilos adicionales si los necesitas */
.hover\:scale-105:hover {
  transform: scale(1.05);
}
</style>
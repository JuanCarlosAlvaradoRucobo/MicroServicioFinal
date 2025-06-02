<!-- App.vue -->
<template>
  <v-app class="bg-background text-white">
    <!-- Barra de navegación -->
    <AppBar />

    <!-- Contenido principal -->
    <v-main>
      <v-container>
        <h1 class="text-h4 text-center mb-6">Sistema de Reportes de Cursos</h1>

        <v-tabs v-model="activeTab" centered>
          <v-tab value="estudiante">Estudiante</v-tab>
          <v-tab value="instructor">Instructor</v-tab>
          <v-tab value="administrador">Administrador</v-tab>
        </v-tabs>

        <v-window v-model="activeTab" class="mt-6">
          <v-window-item value="estudiante">
            <v-row justify="center">
              <v-col cols="12" md="6">
                <ReporteCard
                  userType="estudiante"
                  cursoId="curso123"
                  estudianteId="est456"
                />
              </v-col>
            </v-row>
          </v-window-item>

          <v-window-item value="instructor">
            <v-row justify="center">
              <v-col cols="12" md="6">
                <ReporteCard
                  userType="instructor"
                  cursoId="curso123"
                />
              </v-col>
            </v-row>
          </v-window-item>

          <v-window-item value="administrador">
            <v-row justify="center">
              <v-col cols="12" md="6">
                <ReporteCard
                  userType="administrador"
                  cursoId="curso123"
                />
              </v-col>
            </v-row>
          </v-window-item>
        </v-window>
      </v-container>
    </v-main>

    <!-- Footer -->
    <v-footer app color="primary" class="text-center d-flex justify-center">
      <div class="text-white">
        {{ new Date().getFullYear() }} — <strong>EDMODO</strong>
      </div>
    </v-footer>
  </v-app>
</template>

<script setup>
import { ref } from 'vue';
import { useRouter, useRoute } from 'vue-router'; // 👈 Importamos router y route
import ReporteCard from '../components/Card.vue';

const activeTab = ref('estudiante');

// Instancias del router y la ruta actual
const router = useRouter();
const route = useRoute();

// Ejemplo: cambiar a otra ruta al seleccionar una pestaña (opcional)
function handleTabChange(tab) {
  // Navega a otra ruta si lo necesitas
  // Por ejemplo: router.push(`/dashboard/${tab}`);
  console.log('Tab actual:', tab);
}
</script>


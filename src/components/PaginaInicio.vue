<template>
  <div>
    <!-- Importar el menú -->
    <BarraMenu />

    <!-- Contenido Principal -->
    <div class="welcome-container">
      <h1 class="text-center">¡ Bienvenido a Conect-A !</h1>
      <p class="text-center lead">
        Encuentra compañeros para tus proyectos universitarios y conecta con
        ideas innovadoras.
      </p>
      <div class="text-center mt-4">
        <router-link to="/Proyectos" class="btn btn-primary me-2">Explorar Proyectossss</router-link>
        <router-link to="/Perfiles" class="btn btn-outline-secondary">Buscar Compañeros</router-link>
      </div>
    </div>
  </div>
</template>

<script>
import BarraMenu from "@/components/BarraMenu.vue"; // Importar el menú

export default {
  name: "PaginaInicio",
  components: {
    BarraMenu, // Registra el menú como un componente
  },
  mounted() {
    // Verifica si el usuario está autenticado
    const userId = localStorage.getItem("userId");
    if (!userId) {
      // Si no hay userId, redirige al login
      this.$router.push("/login");
    }
  },
};
</script>

<style scoped>
/* Estilos principales */
.welcome-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  min-height: 80vh;
  background: linear-gradient(135deg, #e9ecef, #f8f9fa);
  padding: 40px 20px;
  border-radius: 10px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
}

h1 {
  font-size: 3rem;
  font-weight: bold;
  color: #495057;
  margin-bottom: 20px;
}

p {
  font-size: 1.25rem;
  color: #6c757d;
  margin-bottom: 30px;
}

.btn {
  padding: 10px 20px;
  font-size: 1rem;
  border-radius: 5px;
}
</style>
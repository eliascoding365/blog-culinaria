<template>
  <nav class="navbar">
    <div class="navbar-brand">
      <a class="navbar-item" href="#">Culinarios</a>
    </div>
    <div>
      <img alt="Vue logo" class="logo" src="@/assets/logo2.jpg" width="120"  />
    </div>
    <div class="navbar-menu">
      <div class="navbar-end">
        <a class="navbar-item" href="/">Inicio</a>
        <a class="navbar-item" href="#">Sobre</a>
        <template v-if="isLoggedIn">
          <button class="navbar-item" @click="logout">Logout</button>
        </template>
        <template v-else>
          <router-link class="navbar-item" to="/login">Login</router-link>
        </template>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  data() {
    return {
      isLoggedIn: false // Defina como true se o usuário estiver logado
    };
  },
  methods: {
    logout() {
      // Implemente a lógica de logout aqui
      // Por exemplo, limpar as credenciais do localStorage e redirecionar para a página de login
      localStorage.removeItem('username');
      localStorage.removeItem('password');
      this.isLoggedIn = false;
      // Redirecione para a página de login
    }
  },
  mounted() {
    // Verifique se o usuário está logado ao montar o componente Navbar
    const storedUsername = localStorage.getItem('username');
    const storedPassword = localStorage.getItem('password');
    
    if (storedUsername && storedPassword) {
      this.isLoggedIn = true;
    }
  }
}
</script>

<style scoped>
.navbar {
  background-color: #333;
  padding: 1em;
  display: flex;
  width: 100%;
  justify-content: space-between;
  align-items: center;
}

.navbar-brand {
  display: flex;
  justify-content: center;
  font-size: 1.5em;
  font-weight: bold;
  color: #fff;
}

.navbar-menu {
  display: flex;
  align-items: center;
}

.navbar-end {
  margin-left: auto;
}

.navbar-item {
  color: #fff;
  text-decoration: none;
  margin-right: 20px;
}

.navbar-item:hover {
  color: #ccc;
}
</style>

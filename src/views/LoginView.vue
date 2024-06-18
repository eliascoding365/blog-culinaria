<template>
  <div class="login">
    <div id="app">
      <h2>Login</h2>
      <form @submit.prevent="submitForm">
        <div>
          <label for="username">Username:</label>
          <input type="text" id="username" v-model="username" required>
        </div>
        <div>
          <label for="password">Password:</label>
          <input type="password" id="password" v-model="password" required>
        </div>
        <button type="submit">Login</button>
      </form>
      <p v-if="errorMessage" style="color: red;">{{ errorMessage }}</p>
      <p v-if="successMessage" style="color: green;">{{ successMessage }}</p>
    </div>
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'Login',
  data() {
    return {
      username: '',
      password: '',
      errorMessage: '',
      successMessage: ''
    };
  },
  mounted() {
    // Verifique se as credenciais estão no localStorage
    const storedUsername = localStorage.getItem('username');
    const storedPassword = localStorage.getItem('password');
    if (storedUsername && storedPassword) {
      this.username = storedUsername;
      this.password = storedPassword;
    }
  },
  methods: {
    submitForm() {
      if (this.username === 'elias' && this.password === '123') {
        this.successMessage = 'Login successful!';
        console.log("Usuario conectado: " + this.username);
        
        // Armazene as credenciais no localStorage
        localStorage.setItem('username', this.username);
        localStorage.setItem('password', this.password);
        
        // Redirecione para a página inicial "/"
        this.$router.push('/');
      } else {
        this.errorMessage = 'Nome de usuário ou senha incorretos. Por favor, tente novamente.';
        this.username = '';
        this.password = '';
      }
    }
  }
}
</script>

<style scoped>
@media (min-width: 1024px) {
  .login {
    min-height: 100vh;
    display: flex;
    justify-content: center;
    margin-top: 100px;
  }
}
</style>

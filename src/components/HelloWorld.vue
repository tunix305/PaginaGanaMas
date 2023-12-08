<template>
  <div class="container pt-5 topContainer" :style="{ backgroundImage: 'url(' + require('@/assets/web/abuelos.png') + ')', backgroundSize: 'cover', height: '65em', display: 'flex', flexDirection: 'column', alignItems: 'center', justifyContent: 'center' }">
    <div>
      <img src="@/assets/web/GC_logo_gray.png" alt="" height="50" class="d-inline-block align-text-bottom">
    </div>
    <div id="app">
      <form @submit.prevent="login" style="text-align: center; background-color: rgba(255, 255, 255, 0.7); padding: 20px; border-radius: 8px; box-shadow: 0 0 10px rgba(0, 0, 0, 0.1); width: 300px; margin: 0 auto;">
        <label for="username">Usuario:</label>
        <input v-model="username" type="text" id="username" name="username" required>

        <label for="password">Contraseña:</label>
        <input v-model="password" type="password" id="password" name="password" required>

        <button type="submit">Iniciar sesión</button>
      </form>

      <div v-if="isLoggedIn" style="margin-top: 20px;">
        <p>Bienvenido, {{ username }}!</p>
        <button @click="logout">Cerrar sesión</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      username: "",
      password: "",
      isLoggedIn: false,
    };
  },
  methods: {
    login() {
      // Lógica de inicio de sesión
      if (this.username === "usuario" && this.password === "contrasena") {
        this.isLoggedIn = true;
      } else {
        alert("Credenciales incorrectas");
      }
    },
    logout() {
      // Lógica de cierre de sesión
      this.isLoggedIn = false;
      this.username = "";
      this.password = "";
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  color: #2c3e50;
  margin-top: 20px;
}

label {
  display: block;
  margin-bottom: 8px;
}

input {
  width: 100%;
  padding: 8px;
  margin-bottom: 16px;
  box-sizing: border-box;
}

button {
  background-color: #4caf50;
  color: #ffffff;
  padding: 10px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  width: 100%;
}

button:hover {
  background-color: #45a049;
}

div {
  margin-top: 20px;
}
</style>

<template>
    <div class="about">
    </div>
    <div class="container pt-5 topContainer" :style="{ backgroundImage: 'url(' + require('@/assets/web/anciano_sentado.png') + ')', backgroundSize: 'cover', height: '100vh', display: 'flex', flexDirection: 'column', alignItems: 'center', justifyContent: 'center', position: 'relative', margin: '0', padding: '0' }">
      <div style="margin-bottom: 550px;"> <!-- Ajusta el valor según tus necesidades -->
        <img src="@/assets/web/GC_logo.png" alt="" height="60" class="d-inline-block align-text-bottom">
      </div>
      <div id="app">
      </div>
      <button class="back-button" @click="back">Regresar</button>
    </div>
    <div>
    </div>
  </template>
  
  <script>
  import { useRoute, useRouter } from 'vue-router';
  
  export default {
    setup() {
      const route = useRoute();
      const router = useRouter();
  
      const back = () => {
        router.push("/HomeView")
      };
      return {
        back,
      };
    },
  };
  </script>
  
  <style scoped>
  body, html {
    margin: 0;
    padding: 0;
    height: 100%;
  }
  
  .back-button {
    position: absolute;
    top: 15px;
    right: 15px;
    padding: 5px 10px;
    background-color: #42b983; /* Color de fondo del botón */
    color: white; /* Color del texto del botón */
    border: none;
    border-radius: 15px;
    cursor: pointer;
    z-index: 1; /* Asegura que el botón esté sobre el fondo */
    font-size: 20px; /* Ajusta el tamaño del texto del botón según tus necesidades */
    width: 100px; /* Ajusta la anchura del botón según tus necesidades */
  }
  </style>
  
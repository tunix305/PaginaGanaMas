<template>
  <div class="about">
  </div>
  <div class="container pt-5 topContainer" :style="{ backgroundImage: 'url(' + require('@/assets/web/abuelo_nieta.png') + ')', backgroundSize: 'cover', height: '65em', display: 'flex', flexDirection: 'column', alignItems: 'center', justifyContent: 'center' }">
    <div style="margin-bottom: 550px;"> <!-- Ajusta el valor según tus necesidades -->
      <img src="@/assets/web/GC_logo.png" alt="" height="60" class="d-inline-block align-text-bottom">
    </div>
    <div class="col-3" @click="load" style="cursor: pointer; text-align: center;">
      <img src="@/assets/web/Gana_mas.png" alt="" height="200" class="image-btn"/>
    </div>
    <div id="app">
    </div>
  </div>
      <button class="back-button" @click="back">salir</button>
  <div>
  </div>
</template>

<script>
import { useRoute, useRouter } from 'vue-router';

export default {
  setup () {
    const route = useRoute();
    const router = useRouter();
    console.log(router);

    const load = () => {
      router.push("/RFC")
    };
    const back = () =>{
      router.push("/")
    };
    return {
      load,
      back,
    };
  },
};
</script>

<style>
.back-button {
    position: absolute;
    top: 30px;
    right: 20px;
    padding: 5px 1px;
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

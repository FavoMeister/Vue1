<script setup lang="ts">
import { ref } from 'vue';

const user = ref({
    id: 1,
    nombre: 'Chad Smith'
});

const guardar = () => {
    console.log("save");
};

function cambiarNombre(event:KeyboardEvent){
  console.log(event);
  const tecla = (event as KeyboardEvent);
  console.log('Tecla Presionada', tecla.key);
  
}

</script>

<template>
  <!-- <div>
    <button class="btn btn-success btn-lg" v-on:click="guardar">Guardar</button>
    <hr>
    <button class="btn btn-success btn-lg" @click="user.nombre='Renzo Roman'">Change Name</button>
    <hr>
    <h2>Name: {{ user.nombre }}</h2>
  </div> -->
  <div class="container">
   <!-- <form action="" @submit.prevent.stop="guardar"> -->
   <form @submit="guardar">
    <div class="mb-3">
      <label for="nombre" class="form-label">Nombre</label>
      <input type="text" name="nombre" id="" class="form-control" @keydown.enter.prevent="cambiarNombre($event)">
    </div>
    <button class="btn btn-primary">Enviar</button>
   </form> 
  </div>
</template>

<style scoped>

</style>

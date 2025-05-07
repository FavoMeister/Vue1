<script setup lang="ts">
import { ref } from 'vue';

const imagenUrl = 'https://picusm.photos/200/300';
let dissabled = ref(true);

setTimeout(() => {
    console.log(dissabled.value);
    dissabled.value = false;
    console.log(dissabled.value);
    
}, 2000);

const propiedadesInput = ref({
    type: 'number',
    disabled: true,
    placeholder: 'Escribir número'
});

</script>

<template>
  <div>
    <input v-bind="propiedadesInput">
    <!-- <img v-bind:src="imagenUrl"> -->
    <img :src="imagenUrl" title="Imagen Aleatoria" alt="Imagen Aleatoria">
    <hr>
    <button v-bind:disabled="dissabled">Botón {{ dissabled ? 'Deshabilitado' : 'Habilitado' }}</button>
  </div>
</template>

<style scoped>

</style>

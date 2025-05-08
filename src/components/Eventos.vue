<script setup lang="ts">
import { ref } from 'vue';

const guardar = () => {
    console.log("save");
};

const user = ref({
    id: 1,
    nombre: 'Chad Smith'
});
</script>

<template>
  <div>
    <button class="btn btn-success btn-lg" v-on:click="guardar">Guardar</button>
    <hr>
    <button class="btn btn-success btn-lg" @click="user.nombre='Renzo Roman'">Change Name</button>
    <hr>
    <h2>Name: {{ user.nombre }}</h2>
  </div>
</template>

<style scoped>

</style>

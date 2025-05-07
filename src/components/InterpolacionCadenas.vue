<script setup lang="ts">
import { ref } from 'vue';

let cuenta = ref<string | number>(1);

setTimeout(() =>{
  console.log('Entro al cambio de variable');
  cuenta.value = 100;
  console.log('Cuenta: ', cuenta);
  
}, 2000);

const carrera = ref({
  id: 1,
  nombre: "Licenciatura en Informática",
  numeroEstudiantes: 100
})
</script>

<template>
  <div>
    <h1>Hola desde el componente Interpolación de Cadenas</h1>
    <p>
        {{ cuenta }}
    </p>

    <input type="text" name="" id="" @input="cuenta = ($event.target as HTMLInputElement).value">
    <hr>
    <b>{{ cuenta }}</b>
    <hr>
    <h2>Carrera <span>{{ carrera.nombre }}</span></h2>
    <h2>Estudiantes <span>{{ carrera.numeroEstudiantes }}</span></h2>

  </div>
</template>

<style scoped>

</style>

<script setup lang="ts">
import { ref } from 'vue';

let isPrimary = ref(true);
let isSamll = ref(true);

const clasesBoton = ref({
    'btn-primary': true,
    'btn-sm': true
})

setTimeout(() => {
    isPrimary.value = false;
    isSamll.value = false;
    clasesBoton.value['btn-primary'] = !clasesBoton.value['btn-primary'];
    clasesBoton.value['btn-sm'] = !clasesBoton.value['btn-sm'];
}, 2500);
</script>

<template>
  <div>
    <h1>Hello con Vue and Bootstrap</h1>
    <hr><hr>
    <button class="btn" :class="clasesBoton">
        Botón Principal
    </button>
  </div>
</template>

<style scoped>

</style>

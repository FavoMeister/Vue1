<script setup lang="ts">
import { ref } from 'vue';

// Objeto de tipo Usuario
type Usuario = {
    id: number,
    nombre: string,
    perfil: string
};

let usuario = ref<Usuario>({
    id: 1,
    nombre: 'Miguel Lata',
    perfil: 'Admin'
})

setTimeout(() => {
    usuario.value.nombre = 'George';
}, 2500);
</script>

<template>
    <div class="container">
        <h1>Directiva Once</h1>
        <div class="alert alert-success" v-once>
            Bienvenido Adiministrado: {{ usuario.nombre }}
        </div>
        <div class="alert alert-primary">
            Bienvenido Directivo: {{ usuario.nombre }}
        </div>
    </div>
</template>

<style scoped>

</style>
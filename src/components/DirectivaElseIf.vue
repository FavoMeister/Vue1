<script setup lang="ts">
import { ref } from 'vue';

// Elemento tipo Usuario
type Usuario = {
    id: number,
    nombre: string,
    perfil: string
};

// Var de tipo Usuario para crear un objeto complejo, pero reactivo
let usuario = ref<Usuario>({
    id: 1,
    nombre: 'Miguel Lata',
    perfil: 'Admin'
})
</script>

<template>
    <div class="container">
        <h1>Directiva Else If</h1>
        <div class="alert alert-success" v-if="usuario.perfil === 'Admin'">
            Bienvenido Adiministrado: {{ usuario.nombre }}
        </div>
        <div class="alert alert-primary" v-else-if="usuario.perfil == 'Directivo'">
            Bienvenido Directivo: {{ usuario.nombre }}
        </div>
        <div class="alert alert-secondary"  v-else-if="usuario.perfil == 'Jefe'">
            Bienvenido Jefe: {{ usuario.nombre }}
        </div>
        <div class="alert alert-warning" v-else>
            Bienvenido Invitado: {{ usuario.nombre }}
        </div>
        <div class="alert alert-danger" v-show="usuario.perfil === 'Admin'">
            Bienvenido: {{ usuario.nombre }}
        </div>
    </div>
</template>

<style scoped>

</style>
<script setup lang="ts">
import { ref } from 'vue';

const estaRegistrado = ref(false);
</script>

<template>
    <div class="container">
        <div class="alert alert-success" v-if="estaRegistrado">
            Bienvenido
        </div>
        <div class="alert alert-secondary" v-else>
            Acceder
        </div>
    </div>
</template>

<style scoped></style>
<script setup lang="ts">
import { ref } from 'vue';

// Tipo de elemento Instrumento
type Instrumento = {
    id: number,
    nombre: string
};

//  Lista de elementos de tipo instrumento
let instrumento: Instrumento[] = [
    {
        id: 1,
        nombre: 'Guitarra'
    },
    {
        id: 2,
        nombre: 'Gaita'
    },
    {
        id: 3,
        nombre: 'Flauta'
    },
    {
        id: 4,
        nombre: 'Acordeón'
    },
    {
        id: 5,
        nombre: 'Piano'
    }
]

// Objeto de tipo usuario
type Usuario = {
    id: number,
    nombre: string,
    apPaterno: string
    apMaterno: string
    carrera: string
};

// Variable de tipo Usuario
const usuario: Usuario = {
    id: 1,
    nombre: 'Federico',
    apPaterno: 'Bueno',
    apMaterno: 'Soto',
    carrera: 'Música'
}

setTimeout(() => {
    //instrumento = 'George';
}, 2500);
</script>

<template>
    <div class="container">
        <h1>Directiva V-For</h1>
        <ul class="list-group">
            <li class="list-group-item" v-for="item in instrumento" :key="item.id">
                {{ item.nombre }}
            </li>
        </ul>
        <hr>
        <ul class="list-group">
            <li class="list-group-item" v-for="(value, key) in usuario">
                {{ key }}: {{ value }}
            </li>
        </ul>
        <hr>
        <ul class="list-group">
            <li class="list-group-item" v-for="numero in 8">
                {{ numero }}
            </li>
        </ul>
    </div>
</template>

<style scoped></style>
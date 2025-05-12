<script setup lang="ts">
import { reactive, toRefs } from 'vue';

type Direccion = {
    calle: string,
    numero: number
}

// Objeto de tipo usuario
type Usuario = {
    id: number,
    nombre: string,
    apPaterno: string
    apMaterno: string
    carrera: string,
    direccion: Direccion
};


// Variable de tipo Usuario
const usuario: Usuario = reactive({
    id: 1,
    nombre: 'Federico',
    apPaterno: 'Bueno',
    apMaterno: 'Soto',
    carrera: 'Engineer',
    direccion: {
        calle: "Murillo",
        numero: 548
    }
});

setTimeout(() => {
    usuario.nombre = "Sophia";
    usuario.carrera = "Math";
    usuario.direccion.calle = 'San Fermin';
    usuario.direccion.numero = 8971;
}, 3500);

let {nombre, carrera} = toRefs(usuario);

setTimeout(() => {
    nombre.value = 'Leyla';
    carrera.value = 'Quimistry'
}, 5050);

</script>

<template>
    <div class="container">
        <h1>Reactive</h1>
        <ul class="list-group">
            <li class="list-group-item">Nombre: {{ usuario.nombre }}</li>
            <li class="list-group-item">Carrera: {{ usuario.carrera }}</li>
            <li class="list-group-item">Dirección: {{ usuario.direccion.calle }} # {{ usuario.direccion.numero }}</li>
        </ul>
        <hr>
        <ul class="list-group">
            <li class="list-group-item">Nombre: {{ usuario.nombre }}</li>
            <li class="list-group-item">Carrera: {{ usuario.carrera }}</li>
        </ul>
    </div>
</template>

<style scoped></style>
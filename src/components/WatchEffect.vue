<script setup lang="ts">
import { reactive, computed, ref, watch, watchEffect } from 'vue';

const producto = reactive({
    nombre: 'Curso Vue',
    cantidad: 10,
    precio: 500
});

const historial = ref<string[]>([]);

const total = computed(() => producto.cantidad * producto.precio);

watch(() => total.value, (nuevoTotal, antiguoTotal) => {
    historial.value.push(`El totla cambió de ${antiguoTotal} a ${nuevoTotal}`);
}, {immediate:true});

watchEffect(() => {
    console.log('Cambio de nombre: ', producto.nombre);
    console.log('Cambio de cantidad: ', producto.cantidad);
    console.log('Cambio de precio: ', producto.precio);
});

</script>

<template>
    <div class="container">
        <h1>Efectos Secundarios con WatchEffect</h1>
        <div class="row">
            <div class="mb-3">
                <label for="nombre" class="form-label">Nombre</label>
                <input type="text" name="" id="nombre" class="form-control" placeholder="#" v-model="producto.nombre">
            </div>
        </div>
        <div class="row">
            <div class="mb-3">
                <label for="cantidad" class="form-label">Cantidad</label>
                <input type="text" name="" id="cantidad" class="form-control" placeholder="#" v-model="producto.cantidad">
            </div>
        </div>
        <div class="row">
            <div class="mb-3">
                <label for="precio" class="form-label">Precio</label>
                <input type="text" name="" id="precio" class="form-control" placeholder="#" v-model="producto.precio">
            </div>
        </div>
        <div class="row">
            <div class="col">
                <h1>Total: $ {{ total }}</h1>
            </div>
        </div>
        <ul>
            <li v-for="(item, indice) in historial" :key="indice">
                {{ item }}
            </li>
        </ul>
    </div>
</template>

<style scoped></style>
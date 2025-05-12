<script setup lang="ts">
import { reactive, computed } from 'vue';

const producto = reactive({
    nombre: 'Curso Vue',
    cantidad: 10,
    precio: 500
});


const total = computed(() => producto.cantidad * producto.precio);

</script>

<template>
    <div class="container">
        <h1>Computed Reactive</h1>
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
    </div>
</template>

<style scoped></style>
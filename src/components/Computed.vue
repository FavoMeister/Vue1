<script setup lang="ts">
import { ref, computed } from 'vue';

const nombre = 'Curso Vue';
const cantidad = ref(10);
const precio = ref(500);

const total = computed(() => cantidad.value * precio.value);

</script>

<template>
    <div class="container">
        <h1>Computed</h1>
        <div class="row">
            <div class="mb-3">
                <label for="cantidad" class="form-label">Cantidad</label>
                <input type="text" name="" id="cantidad" class="form-control" placeholder="#" v-model="cantidad">
            </div>
        </div>
        <div class="row">
            <div class="mb-3">
                <label for="precio" class="form-label">Precio</label>
                <input type="text" name="" id="precio" class="form-control" placeholder="#" v-model="precio">
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
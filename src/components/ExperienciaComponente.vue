<script setup>
import icono1 from '/src/assets/lidera.svg';
import icono2 from '/src/assets/desarrollo.svg';
import icono3 from '/src/assets/estilo.svg';

import { ref } from 'vue';
const titulo = 'Técnico en informática';
const fecha = 'Desde Enero 2019 / Noviembre 2025';
const experiencias = ref([
    { id: 1, src: icono1, parrafo: 'Creación, mantenimiento y backups de servidores' },
    { id: 2, src: icono2, parrafo: 'Servicio técnico en computadoras de escritorio y notebooks.' },
    { id: 3, src: icono3, parrafo: 'Configuracion de redes (routers, AP, WIFI)' }
]);
</script>

<template>
    <div class="card">
        <h3 class="titulo">{{ titulo.toLocaleUpperCase() }}</h3>
        <p class="fecha">{{ fecha }}</p>
        <ul class="listado">
            <li class="item" v-for="experencia in experiencias" :key="experencia.id">
                <img class="imagen-svg" :src="experencia.src" width="45rem" :alt="experencia.parrafo">
                <p>{{ experencia.parrafo }}</p>
            </li>
        </ul>
    </div>
</template>

<style scoped>
.card {
    display: flex;
    flex-direction: column;
    padding: 2rem;
    background-color: rgb(66, 114, 98);
    border-radius: 15px;
}

.titulo {
    font-size: 1.5rem;
    color: rgb(226, 224, 229);
}

.fecha {
    font-size: 1rem;
    color: rgb(225, 173, 104);
    margin-bottom: 1rem;
}

.listado {
    display: flex;
    flex-direction: column;
}

.item {
    align-items: center;
    display: flex;
    padding: 1rem;
    gap: 1.5rem;
}
</style>
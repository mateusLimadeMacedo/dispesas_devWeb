<script setup>
import { useExpenses } from '@/composables/useExpenses'
const {
    filter
} = useExpenses()
</script>
<template>
    <div class="filter">
        <button :class="{ ativo: filter === 'all' }" @click="filter = 'all'">Tudo</button>
        <button :class="{ ativo: filter === 'food'}" @click="filter = 'food'">Comida</button>
        <button :class="{ ativo: filter === 'transport'}" @click="filter = 'transport'">Transporte</button>
        <button :class="{ ativo: filter === 'other'}" @click="filter = 'other'">Outros</button>
    </div>
</template>
<style scoped>
div.filter {
    display: flex;
    gap: 1vw;
    margin-top: 2vw;
}
button {
    background-color: white;
    border: none;
    width: 8vw;
    height: 2.5vw;
    font-size: 20px;
    border-radius: 0.25vw;
    color: #0F172A;
}
.ativo {
    background-color: #1E3A8A ;
    color: white;
}
</style>
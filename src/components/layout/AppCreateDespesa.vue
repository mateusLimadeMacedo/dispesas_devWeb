<script setup>
import { useExpenses } from '@/composables/useExpenses'
const {
    abrir
} = useExpenses()
</script>

<template> 
<button @click="abrir = true">
    <div>
        <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-plus-icon lucide-plus"><path d="M5 12h14"/><path d="M12 5v14"/></svg>
        <p>adicionar gasto</p>
    </div>
</button>
</template>
<style scoped>
button {
    width: 15vw;
    margin-top: 2vw;
    border: none;
    color: white;
    background-color: #1E3A8A;
    border-radius: 0.25vw;
    cursor: pointer;
}
button div {
    display: flex;
    align-items: center;
    justify-content: center;
    height: 2.5vw;
    gap: 0.5vw;
}
button div p { 
    font-size: 1rem;
    width: 11vw;
}
</style>
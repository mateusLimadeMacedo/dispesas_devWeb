<script setup>
import { useExpenses } from '@/composables/useExpenses'




const {
  total
} = useExpenses()
</script>



<template>
<div class="header">
  <div class="summary">
    <h2>Total do dia: </h2>
    <h1>R${{ total.toFixed(2) }}</h1>
  </div>
  <div class="direita">
    <svg xmlns="http://www.w3.org/2000/svg"
       width="30"
       height="30"
       viewBox="0 0 24 24"
       fill="none"
       stroke="currentColor"
       stroke-width="2"
       stroke-linecap="round"
       stroke-linejoin="round">

    <path d="M11 15h2a2 2 0 1 0 0-4h-3c-.6 0-1.1.2-1.4.6L3 17"/>
    <path d="m7 21 1.6-1.4c.3-.4.8-.6 1.4-.6h4c1.1 0 2.1-.4 2.8-1.2l4.6-4.4a2 2 0 0 0-2.75-2.91l-4.2 3.9"/>
    <path d="m2 16 6 6"/>
    <circle cx="16" cy="9" r="2.9"/>
    <circle cx="6" cy="5" r="3"/>

  </svg>
  </div>
</div>
</template>

<style scoped>
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  border-bottom: 1px solid #ddd;
  border-radius: 0.5vw;
  padding-bottom: 10px;
  background: white;
}
.summary {
  margin: 1vw 0 1vw 2vw;
}
.summary h2{
  color: #475569;
  font-size: 15px;
}
.header .summary h1 {
  color: #0F172A;
  font-size: 40px;
}
.direita {
  margin: 0 1vw 3vw 0;
}
svg {
  color: #475569;
}
@media (max-width: 650px){
  .header{
    margin: 0 0 2vw 0 ;
    border-radius: 8px;
  }
  .summary h2{
    font-size: 1.1rem;
  }
  svg {
    margin: 0vw 2vw 15vw 0vw;
  }
}




</style>

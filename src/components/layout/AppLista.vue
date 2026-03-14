<script setup>
import AppItens from '../records/AppItens.vue';
import { useExpenses } from '@/composables/useExpenses'




const {

} = useExpenses()
</script>

<template>
  <div class="panel">
    <h1>Lista do dia</h1>
    <div class="info">
      <h2>Descrição</h2>
      <h2>Categoria</h2>
      <h2>Preço</h2>
    </div>
    <AppItens />
  </div>

</template>

<style scoped>
.panel {
  background: #fff;
  border: 1px solid #ccc;
  padding: 1.5vw;
  margin-top: 1vw;
  border: none;
  border-radius: 0.5vw;
}
.info {
  display: flex;
  justify-content: space-between;
  margin-right: 10vw;
  margin: 0 12vw 0 2vw;
  font-size: 1rem;
  color: #94A3B8;
}
.panel h1 {
  margin: 0 0 8px 0;
  font-size: 1.3vw;
  color: #475569;
  margin-bottom: 1vw;
}

.input {
  width: 100%;
  padding: 6px;
  font-size: 12px;
  border: 1px solid #999;
  margin-bottom: 6px;
}

@media (max-width: 650px){

  .panel{
    margin: 4vh 4vw;
    border-radius: 8px;
  }
  .panel h1{
    font-size: 1.2rem;
    display: flex;
    justify-content: center;
    margin: 3vw;
  }

}




</style>

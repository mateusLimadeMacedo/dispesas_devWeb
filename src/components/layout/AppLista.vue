<script setup>
import AppItens from '../records/AppItens.vue';
import { useExpenses } from '@/composables/useExpenses'




const {
  total
} = useExpenses()
</script>

<template>
  <div class="panel">
    <h2>Lista do dia</h2>
    <table class="table">
      <thead>
        <tr>
          <th>Descricao</th>
          <th>Categoria</th>
          <th>Valor</th>
          <th></th>
        </tr>
      </thead>
      <tbody>
        <AppItens />
      </tbody>

    </table>
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

.panel h2 {
  margin: 0 0 8px 0;
  font-size: 1.3vw;
  color: #475569;
  margin-bottom: 1vw;
}
th {
  font-size: 1vw;
  color: #475569;
}
.input {
  width: 100%;
  padding: 6px;
  font-size: 12px;
  border: 1px solid #999;
  margin-bottom: 6px;
}



.table {
  width: 100%;
  border-collapse: collapse;
  font-size: 12px;
}

.table th,
.table td {
  border-bottom: 1px solid #eee;
  padding: 6px;
  text-align: left;
}

</style>

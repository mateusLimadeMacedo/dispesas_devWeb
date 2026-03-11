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

    <div class="summary">Total do dia: {{ total }}</div>
  </div>
</template>

<style scoped>
.panel {
  background: #fff;
  border: 1px solid #ccc;
  padding: 12px;
}

.panel h2 {
  margin: 0 0 8px 0;
  font-size: 13px;
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

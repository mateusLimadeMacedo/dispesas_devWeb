<script setup>
import { useExpenses } from '@/composables/useExpenses'

const {
  filtered,
  removeExpense
} = useExpenses()
</script>


<template>
    <tr v-for="item in filtered" :key="item.id">
      <td>{{ item.title }}</td>
      <td>{{ item.category }}</td>
      <td>{{ item.value }}</td>
      <td>
        <button class="small-btn" @click="removeExpense(item.id)">X</button>
      </td>
    </tr>
</template>

<style scoped>
.small-btn {
  font-size: 11px;
  padding: 4px 6px;
  border: 1px solid #999;
  background: #eee;
  cursor: pointer;
}
</style>

<script setup>
import AppForm from '@/components/forms/AppForm.vue';
import AppCreateDespesa from '@/components/layout/AppCreateDespesa.vue';
import AppFilterCategory from '@/components/layout/AppFilterCategory.vue';
import AppHeader from '@/components/layout/AppHeader.vue';
import AppLista from '@/components/layout/AppLista.vue';
</script>


<template>
  <div class="app">
    <AppHeader title="Registro de Atividades" />
    <div class="filters">
      <AppFilterCategory />
      <AppCreateDespesa />
    </div>
    <AppLista />
    <AppForm />
  </div>
</template>
<style scoped>
 .app {
  max-width: 1200px;
  margin: 0 auto;
  padding: 24px;
}

.filters {
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-direction: column;
}
.row {
  display: flex;
  gap: 6px;
}




@media (max-width: 650px){

.app{
  padding: 4px;
}



}
</style>

<script setup>
import AppForm from '@/components/forms/AppForm.vue';
import AppHeader from '@/components/layout/AppHeader.vue';
import AppLista from '@/components/layout/AppLista.vue';


</script>


<template>
  <div class="app">
    <AppHeader title="Registro de Atividades" />
    <div class="layout">
    <AppForm />
    <AppLista />
    </div>
  </div>
</template>


<style scoped>
 .app {
  max-width: 1200px;
  margin: 0 auto;
  padding: 24px;
}

.layout {
  display: grid;
  grid-template-columns: 1fr 2fr;
  gap: 18px;
  margin-top: 18px;
}

.row {
  display: flex;
  gap: 6px;
}

</style>

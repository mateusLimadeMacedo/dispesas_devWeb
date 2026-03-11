<script setup>
import { useExpenses } from '@/composables/useExpenses'

const {
  abrir,
  title,
  value,
  category,
  addExpense,
  clearAll
} = useExpenses()
</script>




<template>
  <div class="overlay" v-if="abrir">
    <div class="panel">
      <button class="fechar" @click="abrir = false">
        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none"
          stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"
          class="lucide lucide-x-icon lucide-x">
          <path d="M18 6 6 18" />
          <path d="m6 6 12 12" />
        </svg>
      </button>
      <h2>Nova despesa</h2>
      <div class="form">
        <p>Descrição</p>
        <input v-model="title" class="input" placeholder="digite a descricão" />
      </div>
      <div class="form">
        <p>Categoria</p>
        <input v-model="category" class="input" placeholder="digite a categoria" />
      </div>
      <div class="form">
        <p>Valor</p>
        <input v-model="value" class="input" placeholder="R$0,00" />
      </div>
      <div class="row">
        <button class="salvar" @click="addExpense">Salvar gasto</button>
        <button class="limpar" @click="clearAll">Limpar tudo</button>
      </div>
    </div>
  </div>
</template>

<style scoped>
button.fechar {
  background-color: white;
  border: none;
  width: 2vw;
  height: 2vw;
  border-radius: 100%;
  color: #475569;
}
h2 {
  display: flex;
  justify-content: center;
  font-size: 26px;
}

.overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.6);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 1000;
}

.panel {
  background: #EAEAEA;
  padding: 20px;
  border-radius: 10px;
  width: 25vw;
}
div.form {
  margin: 1vw 0.25vw 1vw 0.25vw;
}
p {
  margin: 0 0.1vw 0.3vw 0.5vw;
  color: #475569;
}
input {
  margin: 0;
  border: none;
  height: 2.5vw;
  padding: 1vw;
  border-radius: 0.5vw;
  font-size: 0.8vw;
}
.row {
  display: flex;
  justify-content: center;
  gap: 1vw;
  margin-top: 2vw;
}
.salvar {
  border: none;
  background-color: #1E3A8A;
  color: white;
  width: 9vw;
  height: 2.5vw;
  border-radius: 0.2vw;
}
.limpar {
  border: none;
  background-color: white;
  width: 9vw;
  height: 2.5vw;
  border-radius: 0.3vw;
}
</style>

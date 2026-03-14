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
  cursor: pointer;
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
  margin: 1vw 0.25vw;
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
  cursor: pointer;
}
.limpar {
  border: none;
  background-color: white;
  width: 9vw;
  height: 2.5vw;
  border-radius: 0.3vw;
  cursor: pointer;
}


@media (max-width: 650px) {

  h2 {
    font-size: 1.5rem;
    margin-bottom: 4vh;

  }

  .panel {
    width: 90%;
    padding: 18px;
  }

  .row {
    flex-direction: column;
    gap: 10px;
  }

  .salvar,
  .limpar {
    width: 100%;
  }

  button.fechar {
    width: 28px;
    height: 28px;
  }
}

div.form p{
  font-size: 1.2rem;
  margin: 4vw 0 1.5vw;

}

input{
  width: 100%;
  height: 6vh;
  border-radius: 8px;
  font-size: 0.8rem;
}

.salvar{
   width: 100%;
    height: 5vh;
    font-size: 0.8rem;
    border-radius: 4px;
    margin: 4vh 0 1vh;
}

.limpar{
  width: 100%;
    height: 5vh;
    font-size: 0.8rem;
    border-radius: 4px;
}

</style>

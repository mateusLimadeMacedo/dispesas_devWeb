<script setup>
import { useExpenses } from '@/composables/useExpenses'

const { filtered, removeExpense } = useExpenses()
</script>

<template>
  <div class="todo">
    <div v-for="item in filtered" :key="item.id" class="despesa">
      <!-- Ícone + título -->
      <div class="icon-title">
        <svg
          v-if="item.category.toLowerCase().trim() === 'food'"
          xmlns="http://www.w3.org/2000/svg"
          width="18"
          height="18"
          viewBox="0 0 24 24"
          fill="none"
          stroke="currentColor"
          stroke-width="2"
          stroke-linecap="round"
          stroke-linejoin="round"
          class="icon lucide-utensils"
          aria-label="Food category icon"
          role="img"
        >
          <path d="M3 2v7c0 1.1.9 2 2 2h4a2 2 0 0 0 2-2V2" />
          <path d="M7 2v20" />
          <path d="M21 15V2a5 5 0 0 0-5 5v6c0 1.1.9 2 2 2h3Zm0 0v7" />
        </svg>

        <svg
          v-if="item.category.toLowerCase().trim() === 'transport'"
          xmlns="http://www.w3.org/2000/svg"
          width="18"
          height="18"
          viewBox="0 0 24 24"
          fill="none"
          stroke="currentColor"
          stroke-width="2"
          stroke-linecap="round"
          stroke-linejoin="round"
          class="icon lucide-car"
        >
          <path d="M19 17h2c.6 0 1-.4 1-1v-3c0-.9-.7-1.7-1.5-1.9C18.7 10.6 16 10 16 10s-1.3-1.4-2.2-2.3c-.5-.4-1.1-.7-1.8-.7H5c-.6 0-1.1.4-1.4.9l-1.4 2.9A3.7 3.7 0 0 0 2 12v4c0 .6.4 1 1 1h2"/>
          <circle cx="7" cy="17" r="2"/>
          <path d="M9 17h6"/>
          <circle cx="17" cy="17" r="2"/>
        </svg>

        <svg
          v-if="item.category.toLowerCase().trim() === 'other'"
          xmlns="http://www.w3.org/2000/svg"
          width="18"
          height="18"
          viewBox="0 0 24 24"
          fill="none"
          stroke="currentColor"
          stroke-width="2"
          stroke-linecap="round"
          stroke-linejoin="round"
          class="icon lucide-ellipsis"
        >
          <circle cx="12" cy="12" r="1"/>
          <circle cx="19" cy="12" r="1"/>
          <circle cx="5" cy="12" r="1"/>
        </svg>

        <h1 class="title">{{ item.title }}</h1>
      </div>

        <p class="categoria">{{ item.category }}</p>
        <p class="valor">R${{ item.value.toFixed(2) }}</p>


      <button class="small-btn" @click="removeExpense(item.id)"><svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-trash2-icon lucide-trash-2"><path d="M10 11v6"/><path d="M14 11v6"/><path d="M19 6v14a2 2 0 0 1-2 2H7a2 2 0 0 1-2-2V6"/><path d="M3 6h18"/><path d="M8 6V4a2 2 0 0 1 2-2h4a2 2 0 0 1 2 2v2"/></svg></button>
    </div>
  </div>
</template>

<style scoped>
.todo {
  display: flex;
  flex-direction: column;
  gap: 12px;
}

/* Card de cada despesa */
.despesa {
  display: flex;
  align-items: center;
  justify-content: space-between;
  background-color: #EAEAEA;
  border-radius: 3px;
  padding: 4px 12px;
  gap: 12px;
}


.icon-title {
  display: flex;
  align-items: center;
  width: 12vw;
  max-width: 10vw;
  gap: 8px;
}

.icon {
  color: #3B82F6;
}

.title {
  font-size: 1rem;
  font-weight: 600;
  margin: 0;
}


.details {
  display: flex;
  flex-direction: column;
  align-items: flex-end;
  gap: 2px;
}
.despesa p.categoria {
  width: 12vw;
  max-width: 10vw;
}


.small-btn {
  font-size: 11px;
  padding: 4px 6px;
  border: none;
  background: #EAEAEA;
  color: #475569;
  cursor: pointer;
}
</style>
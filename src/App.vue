<script setup lang="ts">
import { ref, onMounted } from 'vue'
import axios from 'axios'

const API_URL = 'http://localhost:3001/tasks'

interface Task {
  id: number
  title: string
  completed: boolean
}

const tasks = ref<Task[]>([])
const title = ref('')

const loadTasks = async () => {
  const res = await axios.get(API_URL)
  tasks.value = res.data
}

const addTask = async () => {
  if (!title.value.trim()) return

  await axios.post(API_URL, {
    task: {
      title: title.value,
      completed: false
    }
  })

  title.value = ''
  await loadTasks()
}

const toggleTask = async (id: number) => {
  const task = tasks.value.find(t => t.id === id)

  if (!task) return

  await axios.put(`${API_URL}/${id}`, {
    task: {
      completed: !task.completed
    }
  })

  await loadTasks()
}

const deleteTask = async (id: number) => {
  await axios.delete(`${API_URL}/${id}`)
  await loadTasks()
}

onMounted(loadTasks)
</script>

<template>
  <div class="container">
    <h1>Lista de Tarefas</h1>

    <input
      v-model="title"
      type="text"
      placeholder="Nova tarefa"
    />

    <button @click="addTask">Adicionar</button>

    <ul>
      <li v-for="task in tasks" :key="task.id">

        <input
          type="checkbox"
          :checked="task.completed"
          @change="toggleTask(task.id)"
        >

        <span
          :style="{
            textDecoration: task.completed ? 'line-through' : 'none'
          }"
        >
          {{ task.title }}
        </span>

        <button @click="deleteTask(task.id)">
          🗑️
        </button>

      </li>
    </ul>
  </div>
</template>

<style scoped>
.container {
  text-align: center;
  padding: 20px;
  min-height: 100vh;
  background: black;
}

h1 {
  font-size: 2.5rem;
  color: greenyellow;
}

input {
  padding: 10px;
  margin: 10px;
}

button {
  padding: 10px;
  margin-left: 5px;
  cursor: pointer;
}

li {
  list-style: none;
  margin: 15px;
  font-size: 1.3rem;
  color: greenyellow;
}

.done {
  text-decoration: line-through;
  opacity: 0.7;
}
</style>
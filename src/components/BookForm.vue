<template>
  <form @submit.prevent="submitForm" class="form">
    <input v-model="title" placeholder="Judul Buku" required />
    <input v-model="author" placeholder="Penulis" required />
    <textarea v-model="description" placeholder="Deskripsi" required></textarea>
    <button type="submit">Tambah Buku</button>
  </form>
</template>

<script setup>
import { ref } from 'vue'
const emit = defineEmits(['add-book'])

const title = ref('')
const author = ref('')
const description = ref('')

function submitForm() {
  emit('add-book', {
    title: title.value,
    author: author.value,
    description: description.value
  })
  title.value = ''
  author.value = ''
  description.value = ''
}
</script>

<style scoped>
.form {
  display: flex;
  flex-direction: column;
  gap: 10px;
  margin-bottom: 20px;
  width: 100%;
}
input, textarea {
  padding: 8px;
  border: 1px solid #8e24aa;
  border-radius: 5px;
  font-size: 1rem;
  width: 100%;
  box-sizing: border-box;
}
button {
  padding: 10px;
  background-color: #7b1fa2;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  font-size: 1rem;
}
button:hover {
  background-color: #6a1b9a;
}
</style>

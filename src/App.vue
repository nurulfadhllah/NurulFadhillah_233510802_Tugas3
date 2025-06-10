<template>
  <div class="app-container">
    <h1 class="header">📚 Daftar Buku Perpustakaan</h1>
    <BookForm @add-book="addBook" />
    <BookList :books="books" @show-book="handleShowBook" />
    <BookDetail>
      <template v-if="selectedBook" #default>
        <h2>{{ selectedBook.title }}</h2>
        <p><strong>Penulis:</strong> {{ selectedBook.author }}</p>
        <p><strong>Deskripsi:</strong> {{ selectedBook.description }}</p>
      </template>
    </BookDetail>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import BookForm from './components/BookForm.vue'
import BookList from './components/BookList.vue'
import BookDetail from './components/BookDetail.vue'

const books = ref([
  { id: 1, title: 'Laskar Pelangi', author: 'Andrea Hirata', description: 'Kisah anak-anak di Belitung' },
  { id: 2, title: 'Bumi', author: 'Tere Liye', description: 'Petualangan remaja dunia paralel' }
])
const selectedBook = ref(null)

function handleShowBook(book) {
  selectedBook.value = book
}

function addBook(newBook) {
  newBook.id = Date.now()
  books.value.push(newBook)
}
</script>

<style scoped>
html, body, #app {
  height: 100%;
  margin: 0;
  padding: 0;
}
.app-container {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
  padding: 30px;
  background-color: #f3e5f5;
  font-family: Arial, sans-serif;
  color: #4a148c;
  box-sizing: border-box;
}
.header {
  font-size: 28px;
  margin-bottom: 20px;
  color: #8e24aa;
  text-align: center;

}
@media (max-width: 1024px) {
  .app-container {
    padding: 20px;
  }
  .header {
    font-size: 24px;
  }
}
@media (max-width: 600px) {
  .app-container {
    padding: 15px;
  }
  .header {
    font-size: 20px;
  }
}
</style>
<template>
  <div class="book-list">
    <BookItem
      v-for="book in books"
      :key="book.id"
      :book="book"
      @click="$emit('show-book', book)"
    />
  </div>
</template>

<script setup>
import BookItem from './BookItem.vue'
defineProps(['books'])
</script>

<style scoped>
.book-list {
  width: 100%;
}
</style>

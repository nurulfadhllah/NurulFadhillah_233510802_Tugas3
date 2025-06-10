<template>
  <div @click="$emit('click')" class="book-item">
    {{ book.title }} - {{ book.author }}
  </div>
</template>

<script setup>
defineProps(['book'])
</script>

<style scoped>
.book-item {
  padding: 10px;
  margin: 5px 0;
  cursor: pointer;
  border: 1px solid #ce93d8;
  border-radius: 4px;
  background-color: #f3e5f5;
  font-size: 1rem;
}
.book-item:hover {
  background-color: #e1bee7;
}
</style>
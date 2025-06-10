<template>
  <button class="btn" @click="kirimPesan">Kirim Pesan ke Parent</button>
</template>

<script>
export default {
  methods: {
    kirimPesan() {
      this.$emit('dataDikirim', 'Halo dari ChildComponent.vue!')
    }
  }
}
</script>

<style scoped>
.btn {
  background-color: palevioletred;
  color: white;
  padding: 10px 20px;
  border: none;
  border-radius: 8px;
  font-size: 1em;
  cursor: pointer;
  transition: background-color 0.3s;
}

.btn:hover {
  background-color: grey;
}
</style>

<template>
  <div class="parent">
    <!-- Emit Section -->
    <section class="card">
      <h2>🎯 Contoh Nested Emit</h2>
      <ChildComponent @dataDikirim="tampilkanData" />
      <p v-if="pesan" class="output">Pesan dari Child: <strong>{{ pesan }}</strong></p>
    </section>

    <!-- Slot Section -->
    <section class="card">
      <h2>🧩 Contoh Slot</h2>
      <CardComponent>
        <p>📌 Konten ini disisipkan oleh <code>ParentComponent.vue</code> ke dalam slot Card.</p>
      </CardComponent>
    </section>
  </div>
</template>

<script>
import ChildComponent from './ChildComponent.vue'
import CardComponent from './CardComponent.vue'

export default {
  name: 'ParentComponent',
  components: { ChildComponent, CardComponent },
  data() {
    return {
      pesan: ''
    }
  },
  methods: {
    tampilkanData(data) {
      this.pesan = data
    }
  }
}
</script>

<style scoped>
.parent {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
  padding: 40px 20px;
  background: palevioletred;
  font-family: 'Segoe UI', sans-serif;
  box-sizing: border-box;
}

.card {
  background: pink;
  padding: 60px 40px;
  margin-bottom: 32px;
  border-radius: 12px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
  transition: box-shadow 0.3s ease;
}

.card:hover {
  box-shadow: 0 6px 16px rgba(0, 0, 0, 0.15);
}

h2 {
  margin-bottom: 16px;
  color: #333;
}

.output {
  margin-top: 12px;
  font-size: 1.1em;
  color: #333;
}
</style>

<style>
html, body {
  height: 100%;
  margin: 0;
  padding: 0;
}
</style>

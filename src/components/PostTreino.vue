<template>
  <div class="post">
    <h3>{{ usuario }}</h3>

    <p class="descricao">
      {{ descricao }}
    </p>

    <ul>
      <li v-for="ex in exercicios" :key="ex">
        {{ ex }}
      </li>
    </ul>

    <button class="like">❤️ Curtir</button>
  </div>
</template>

<script setup>
defineProps({
  usuario: String,
  descricao: String,
  exercicios: Array
})
</script>

<style scoped>
.post {
  background: #111;
  padding: 20px;
  border-radius: 10px;
  margin-bottom: 20px;
  border: 1px solid #1e90ff;
}

h3 {
  color: #1e90ff;
}

.descricao {
  margin: 10px 0;
}

ul {
  margin-bottom: 10px;
}

.like {
  background: #1e90ff;
  border: none;
  padding: 8px 15px;
  border-radius: 6px;
  color: white;
  cursor: pointer;
}
</style>
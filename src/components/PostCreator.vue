<template>
  <div class="post-creator">

    <h2>Criar Post</h2>

    <input type="file" @change="previewImage">

    <!-- preview -->
    <div v-if="imagePreview" class="preview">
      <img :src="imagePreview" alt="preview">
    </div>

    <button @click="createPost">Postar</button>

  </div>
</template>

<script setup>
import { ref } from 'vue'

const imagePreview = ref(null)

function previewImage(event) {
  const file = event.target.files[0]

  if (!file) return

  const reader = new FileReader()

  reader.onload = (e) => {
    imagePreview.value = e.target.result
  }

  reader.readAsDataURL(file)
}

function createPost() {
  alert("Post criado (temporário)")
}
</script>

<style scoped>

.post-creator{
  background:#111;
  padding:20px;
  border-radius:10px;
  margin-bottom:20px;
}

input{
  margin:10px 0;
}

.preview img{
  width:100%;
  max-width:300px;
  border-radius:10px;
}

button{
  background:#00ff88;
  border:none;
  padding:10px 20px;
  border-radius:8px;
  cursor:pointer;
}

</style>
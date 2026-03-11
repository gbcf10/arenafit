<template>
  <div class="feed">

    <h1>ArenaFit Feed</h1>

    <!-- FORM -->
    <div class="post-form">

      <textarea
        v-model="text"
        placeholder="Compartilhe seu treino..."
      ></textarea>

     <input type="file" @change="handleFile">

<img
  v-if="preview"
  :src="preview"
  class="post-img"
/>

<button @click="createPost">
  Postar
</button>

    </div>

    <!-- POSTS -->
    <div
      v-for="(post, index) in posts"
      :key="index"
      class="post"
    >

      <p>{{ post.text }}</p>

      <img
        v-if="post.image"
        :src="post.image"
        class="post-img"
      >
      <div class="like-area">

  <p>❤️ {{ post.likes }} curtidas</p>

  <button @click="likePost(index)">
    Curtir
  </button>

</div>

    </div>

  </div>
</template>

<script setup>
import { ref } from 'vue'

const text = ref('')
const file = ref(null)
const posts = ref([])
const preview = ref(null)

function handleFile(event) {

  file.value = event.target.files[0]

  if (file.value) {
    preview.value = URL.createObjectURL(file.value)
  }

}

function createPost() {

  let imageUrl = null

  if (file.value) {
    imageUrl = URL.createObjectURL(file.value)
  }

 posts.value.unshift({
  text: text.value,
  image: imageUrl,
  likes: 0
})

  text.value = ''
  file.value = null
  preview.value = null

}

function likePost(index) {
  posts.value[index].likes++
}
</script>

<style scoped>

.feed {
  max-width: 600px;
  margin: auto;
}

.post-form {
  display: flex;
  flex-direction: column;
  gap: 10px;
  margin-bottom: 30px;
}

.post {
  border: 1px solid #ddd;
  padding: 10px;
  margin-bottom: 20px;
}

.post-img {
  width: 100%;
  margin-top: 10px;
}
.like-area{
  margin-top:10px;
}

.like-area button{
  padding:5px 10px;
  cursor:pointer;
} 
</style>
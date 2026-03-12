<template>
  <div class="feed">

 <h1 class="feed-title">ArenaFit Feed</h1>

    <!-- FORM -->
    <div class="post-form">

      <textarea
        v-model="text"
        placeholder="Compartilhe seu treino..."
      ></textarea>

      <input type="file" @change="handleFile">

     <div v-if="preview" class="preview-container">

  <img
    :src="preview"
    class="post-img"
  />

  <button class="remove-image" @click="removeImage">
    ✕
  </button>

</div>
      
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

        <button @click="deletePost(index)">
          Excluir
        </button>

      </div>

    </div>

    <!-- MODAL DE CONFIRMAÇÃO -->
    <div v-if="showDeleteModal" class="modal-overlay">

      <div class="modal">

        <h3>Excluir post?</h3>

        <p>Tem certeza que deseja excluir este post?</p>

        <div class="modal-buttons">

          <button @click="cancelDelete">
            Cancelar
          </button>

          <button @click="confirmDelete">
            Excluir
          </button>

        </div>

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

const showDeleteModal = ref(false)
const postToDelete = ref(null)

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

function deletePost(index) {
  postToDelete.value = index
  showDeleteModal.value = true
}

function confirmDelete() {
  posts.value.splice(postToDelete.value, 1)

  showDeleteModal.value = false
  postToDelete.value = null
}

function cancelDelete() {
  showDeleteModal.value = false
  postToDelete.value = null
}
function removeImage() {
  file.value = null
  preview.value = null
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
  display:flex;
  gap:10px;
}

.like-area button{
  padding:5px 10px;
  cursor:pointer;
}

/* modal base (você pode melhorar depois) */

.modal-overlay{
  position:fixed;
  top:0;
  left:0;
  width:100%;
  height:100%;
  background:rgba(0,0,0,0.75);
  display:flex;
  justify-content:center;
  align-items:center;
  z-index:1000;
}

.modal{
  background:white;
  color: #111;
  padding:25px;
  border-radius:12px;
  width:320px;
  text-align:center;
  box-shadow:0 10px 30px rgba(0,0,0,0.6);
}

.modal h3{
  margin-bottom:10px;
}

.modal p{
  font-size:14px;
  color:#333;
}

.modal-buttons{
  margin-top:20px;
  display:flex;
  justify-content:center;
  gap:15px;
}

.modal-buttons button{
  padding:8px 18px;
  border:none;
  border-radius:6px;
  cursor:pointer;
  font-weight:500;
}

.modal-buttons button:first-child{
  background:#444;
  color:white;
}

.modal-buttons button:last-child{
  background:#ff3b3b;
  color:white;
}

.modal{
  background:white;
  padding:20px;
  border-radius:10px;
  text-align:center;
}

.modal-buttons{
  margin-top:15px;
  display:flex;
  justify-content:space-between;
}
.preview-container{
  position:relative;
  width:100%;
}

.remove-image{
  position:absolute;
  top:8px;
  right:8px;
  background:rgba(0,0,0,0.7);
  color:white;
  border:none;
  border-radius:50%;
  width:28px;
  height:28px;
  cursor:pointer;
  font-size:16px;
  display:flex;
  align-items:center;
  justify-content:center;
}

.remove-image:hover{
  background:red;
}

</style>
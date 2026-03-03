<template>
  <div class="app">
    <Navbar />
    <router-view />
  </div>
</template>

<script setup>
import Navbar from './components/Navbar.vue'
</script>

<style>
body {
  margin: 0;
  font-family: Arial, sans-serif;
  background: #0f0f0f;
  color: white;
}

.app {
  min-height: 100vh;
}
</style>
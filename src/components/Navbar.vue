<template>
  <nav class="navbar">
    <h2 class="logo">🏋️ ArenaFit</h2>

    <div class="links">
      <router-link to="/">Home</router-link>
      <router-link to="/feed">Feed</router-link>
      <router-link to="/login">Login</router-link>
    </div>
  </nav>
</template>

<style scoped>
.navbar {
  width: 100%;
  padding: 15px 30px;
  background: #111;
  display: flex;
  justify-content: space-between;
  align-items: center;
  border-bottom: 1px solid #1e90ff;
}

.logo {
  color: #1e90ff;
}

.links a {
  color: white;
  margin-left: 20px;
  text-decoration: none;
}

.links a.router-link-active {
  color: #1e90ff;
}
</style>
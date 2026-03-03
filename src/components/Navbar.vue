<template>
  <nav class="navbar">
    <h2 class="logo">🏋️ ArenaFit</h2>

    <div class="links">
      <router-link to="/">Home</router-link>
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
  font-weight: bold;
}

.links a {
  color: white;
  text-decoration: none;
  margin-left: 20px;
}

.links a.router-link-active {
  color: #1e90ff;
}
</style>
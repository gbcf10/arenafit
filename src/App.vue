<template>

  <nav class="navbar">

    <h2>ArenaFit</h2>

    <div class="links">
      <router-link to="/">Home</router-link>
      <router-link to="/feed">Feed</router-link>
      <router-link to="/login">Login</router-link>
    </div>

  </nav>

  <router-view />

</template>

<style>

body{
  margin:0;
  background:#0f0f0f;
  color:white;
  font-family:Arial;
}

.navbar{
  display:flex;
  justify-content:space-between;
  align-items:center;
  padding:15px 40px;
  background:#111;
  border-bottom:1px solid #222;
}

.links a{
  color:white;
  margin-left:20px;
  text-decoration:none;
}

.links a:hover{
  color:#42b883;
}

</style>
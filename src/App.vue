<template>

  <nav class="navbar">

    <div class="brand">
      <h2>ArenaFit</h2>

      <img 
        src="/src/assets/logo.JPG"
        class="logo"
      />
    </div>

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

/* NAVBAR */

.navbar{
  display:flex;
  justify-content:space-between;
  align-items:flex-start;
  padding:15px 40px;
  background:#111;
  border-bottom:1px solid #222;
}

/* ARENAFIT + LOGO */

.brand{
  display:flex;
  flex-direction:column;
}

.logo{
  width:80px;
  margin-top:-20px;
}

/* LINKS */

.links a{
  color:white;
  margin-left:20px;
  text-decoration:none;
}

.links a:hover{
  color:#42b883;
}

</style>
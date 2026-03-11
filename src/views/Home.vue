<template>

  <div class="home">

    <h1>ArenaFit</h1>

    <p>
      A rede social para quem vive o treino.
      Compartilhe seus resultados, evolução
      e inspire outros atletas.
    </p>

    <div class="buttons">

      <router-link to="/feed" class="btn">
        Entrar no Feed
      </router-link>

      <router-link to="/login" class="btn-outline">
        Fazer Login
      </router-link>

    </div>

  </div>

</template>

<style scoped>

.home{
  height:80vh;
  display:flex;
  flex-direction:column;
  justify-content:center;
  align-items:center;
  text-align:center;
}

h1{
  font-size:48px;
  margin-bottom:10px;
}

p{
  max-width:500px;
  color:#aaa;
  margin-bottom:30px;
}

.buttons{
  display:flex;
  gap:20px;
}

.btn{
  background:#42b883;
  padding:12px 25px;
  border-radius:6px;
  text-decoration:none;
  color:white;
}

.btn-outline{
  border:1px solid #42b883;
  padding:12px 25px;
  border-radius:6px;
  text-decoration:none;
  color:#42b883;
}

.btn:hover{
  opacity:0.9;
}

</style>
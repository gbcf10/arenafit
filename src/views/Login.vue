<template>
  <div class="login">
    <h1>Login ArenaFit</h1>

    <input type="email" placeholder="Email" />
    <input type="password" placeholder="Senha" />

    <button>Entrar</button>
  </div>
</template>

<style scoped>
.login {
  max-width: 400px;
  margin: 80px auto;
  display: flex;
  flex-direction: column;
  gap: 15px;
}

input {
  padding: 10px;
  border-radius: 6px;
  border: none;
}

button {
  padding: 10px;
  background: #1e90ff;
  border: none;
  color: white;
  border-radius: 6px;
  cursor: pointer;
}
</style>
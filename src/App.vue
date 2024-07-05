<script setup>
import { ref } from 'vue'
const username = ref('')
const email = ref('')
const password = ref('')

</script>

<template>
  <main>
    <h1>Pintorest</h1>
    <h4 style="font-weight: 400;">Bem-vindo(a) ao meu <span style="font-weight: bold;">Pintorest</span></h4>
    <form>
      <div>
        <label for="username">Usuário:</label>
        <input type="text" id="username" v-model="username" />
      </div>
      <div>
        <label for="email">Email:</label>
        <input type="email" id="email">
      </div>
      <div>
        <label for="password">Senha:</label>
        <input type="password" id="password" v-model="password" />
      </div>
      <div>
        <label for="password">Confirme a senha:</label>
        <input type="password" id="password" v-model="repassword" />
      </div>
      <div>
        <input type="date" v-model="date" placeholder="Data de Nascimento" required />
      </div>
      <div>
        <p style="white-space: pre-line;">Preferências</p>
        <textarea v-model="pref" />
      </div>
      <button type="submit">Login</button>
      <h4 style="font-weight: 400;">OU</h4>
      <button type="google">Continuar com o Google</button>

      <div style="margin: 20px;">
        <p><h6 style="font-weight: 400;">
          Ao continuar, você concorda com os <span style="font-weight: bold;">Termos de Serviço</span> do Pintorest e confirma que leu nossa
          <span style="font-weight: bold;">Política de Privacidade.</span>
        <p style="font-weight: bold;">Aviso na coleta de informações.</p>
        </h6></p>
        <hr>
        <p><h6 style="font-weight: 400;">
          <span style="font-weight: bold;">Ainda não está no Pinterest?</span> Crie uma conta. Comece aqui!
        </h6></p>
      </div>
    </form>
  </main>
  <footer></footer>
</template>

<style scoped>
main {
  text-align: center;
}
main h1 {
  color: rgb(226, 51, 51);
  font-size: 60px;
}
form {
  max-width: 300px;
  margin:auto;
  padding: 20px;
  border-radius: 15px;
}
label {
  font-weight: bold;
}
input[type='text'],
input[type='password'],
input[type='email'] {
  width: 100%;
  padding: 8px;
  margin: 5px 0 10px;
  box-sizing: border-box;
  border-radius: 10px;
  border: 1.5px solid;
}
button[type='submit']{
  background-color: rgb(226, 51, 51);
  color: white;
  padding: 10px 20px;
  border: none;
  cursor: pointer;
  border-radius: 20px;
  width: 100%;
}
button[type='submit']:hover {
  background-color: rgb(153, 34, 34);
}
button[type='google']{
  color: rgb(46, 46, 46);
  padding: 10px 20px;
  border: 1px solid ;
  border-color: rgb(46, 46, 46);
  cursor: pointer;
  border-radius: 20px;
  width: 100%;
}
button[type='google']:hover {
  background-color: rgb(214, 214, 214);
}
</style>

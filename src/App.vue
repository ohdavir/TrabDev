<script setup>
import { ref } from 'vue'
const username = ref('')
const email = ref('')
const password = ref('')
const date = ref('')
const pref = ref('')
const resultados = ref(false)
const sumir = ref(true)

function Sumir() {
  sumir.value = !sumir.value

}
function Resultados(){
  resultados.value = !resultados.value
}

</script>

<template>
  <main>
    <h1>Pintorest</h1>
    <h4 style="font-weight: 400;">Bem-vindo(a) ao meu <span style="font-weight: bold;">Pintorest</span></h4>
    <form @submit.prevent="">
      <div v-if="sumir">
      <div>
        <label for="username">Usuário:</label>
        <input type="text" id="username" v-model="username" required/>
      </div>

      <div>
        <label for="email">Email:</label>
        <input type="email" id="email" v-model="email" required/>
      </div>

      <div>
        <label for="password">Senha:</label>
        <input type="password" id="password" v-model="password" required/>
      </div>

      <div>
        <label for="password">Confirme a senha:</label>
        <input type="password" id="password" v-model="repassword" required/>
      </div>  

      <div>
        <input type="date" id="date" v-model="date" placeholder="Data de Nascimento" required/>
      </div>

      <div>
        <p style="white-space: pre-line;">Preferências</p>
        <textarea v-model="pref" name="" id="pref" cols="30" rows="10" required></textarea>
      </div>
  
    </div>
    <div v-if="resultados" @click="Resultados" id="resultados">
      <h3>Resultados</h3>
      <br>
      <p>Nome de Usuário: <span style="font-weight: 300;"> {{ username }}</span></p>
      <br>
      <p>Email: <span style="font-weight: 300;">{{ email }}</span></p>
      <br>
      <p>Senha: <span style="font-weight: 300;">{{ password }}</span></p>
      <br>
      <p>Data de Nascimento: <span style="font-weight: 300;">{{ date }}</span></p>
      <br>
      <p>Preferências: <span style="font-weight: 300;">{{ pref }}</span></p>
      <br>
    </div>
      <button style="font-weight: bold;" @click="Resultados(),Sumir()" type="submit"> <span  v-if="sumir" >Login</span><span v-if="resultados">Voltar</span></button>

      <h4  v-if="sumir" style="font-weight: 400;">OU</h4>

      <button  v-if="sumir" type="google">Continuar com o Google</button>

      <div style="margin: 20px;">
        <p><h6 style="font-weight: 400;">
          Ao continuar, você concorda com os <span style="font-weight: bold;">Termos de Serviço</span> do Pintorest e confirma que leu nossa
          <span style="font-weight: bold;">Política de Privacidade.</span>
        <p style="font-weight: bold;">Aviso na coleta de informações.</p>
        </h6></p>
        <hr>
        <p v-if="sumir"><h6 style="font-weight: 400;">
          <span style="font-weight: bold;">Ainda não está no Pinterest?</span> Crie uma conta. Comece aqui! 
        </h6></p>
      </div>
    </form>
  </main>
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
  margin-top: 12px;
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
#naoTemConta{
  border: none;
  background-color: white;
  font-weight: bold;
  margin-top: 22px;
}
</style>

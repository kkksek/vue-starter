<template>
  <div class="my-app">
    <h1>System do zapisów na zjęcia</h1>
	<div v-if="loggedIn">
	Witaj: {{ email }}<br>
	<button @click="logMeOut()">Wyloguj</button>
	</div>
	
	<div v-else>
	<LoginForm @login="(username) => logMeIn(username)" button-label="Wejdź"></LoginForm>
	<LoginForm @login="(username) => logMeIn(username)" button-label="Wleć"></LoginForm>
	<LoginForm @login="(username) => logMeIn(username)":button-label="Math.random() < 0.5 ? 'Etykieta A' : 'Etykieta B'"></LoginForm>
	</div>
	</div>
	
	
	<!--<div v-if="!email.includes('@')">Twój adres email jest niepoprawny</div>
	<div v-else-if="email.length < 10">Ale masz krótki adres!</div>
	<div v-else-if="email.length < 15">Twój adres e-mail jest w sam raz.</div>
	<div v-else>Twój adres e-mail jest stanowczo za długi.</div>-->
 	<!--<div>Posiada: {{email.length}} znaków</div> -->
	
	
  </div>
	
</template>

<script>
import "milligram";
import LoginForm from "./LoginForm";
export default {
components: {LoginForm},
data() {
  return {
    email: 'ksek@agh.edu.pl',
	loggedIn: false,
    password: ''
  };
},
methods:{
logMeIn(username){
this.loggedIn=true;
this.email = username;
},
logMeOut(){
this.loggedIn=false;
}
}
}
</script>

<style>
.my-app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: left;
  color: #2c3e50;
}
</style>

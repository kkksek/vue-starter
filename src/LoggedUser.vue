<template>
   <div>
   Witaj: {{email}} <br>
	<button @click="enter()">{{buttonLabel}}</button>
   </div>
   </template>
   <script>
   
export default {
 props: {
     buttonLabel: String,
 },
 data() {
     return {
         email: ''
     }
 },
 methods: {
     enter() {
         this.$emit('loggedUserEmail', this.email);
     }
 }
}
</script>
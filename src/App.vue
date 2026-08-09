<template>
  <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  <h1 class="p-8 text-xl">{{ info }}</h1>
  <h2>Vue test</h2>
  <div class ="flex flex-col px-4 max-w-300 mx-auto my-2">
    <input type="text" class="p-2 mt-2 border rounded-xs" v-model="userName" @input="insertData($event.target.value)" placeholder="Name" id="User" />
    <input type="password" class="p-2 mt-2 border rounded-xs" v-model="userPassword" placeholder="Passwort" id="passwort" />
    <input type="email" class="p-2 mt-2 border rounded-xs" v-model="userEmail" placeholder="Email" id="Email" />
  </div>


  <button class="bg-red-500 text-white py-4 px-6 border rounded-sm" @click="addUser()">Click</button>
  <div v-if="users.length <= 0">Es gibt keine Users</div>
  <UserProfil v-for="(el, index) in users" :key="index" :user="el" @click="deleteUser(index)"></UserProfil>
</template>
<script>

import UserProfil from './components/UserProfil.vue'
/* import HelloWorld from './components/HelloWorld.vue' */

export default {
  name: 'App',
  components: {
    UserProfil
  },
  data(){
    return {
      info: "Title", 
      andereTest: "Text",
      users: [],
      userName: "",
      userPassword: "",
      userEmail: ""
    }
  },
  methods:{
    userData(){
      this.info = 'Neutitle';
    },
    insertData(val){
      return this.userName = val;
    },
    addUser(){
      if(this.userName != "" && this.userPassword != "" && this.userEmail != "")
      this.users.push({
        name: this.userName,
        email: this.userEmail,
        password: this.userPassword
      })
    }, 
    deleteUser(indexUser){
      this.users.splice(indexUser, 1);
    },
  }
}
</script>

<style>
h2{
  color:red;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;

}
</style>

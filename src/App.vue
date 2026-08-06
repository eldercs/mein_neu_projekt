<template>
  <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  <p>{{ info }}</p>
  <h2>Vue test</h2>
  <input type="text" v-model="userName" @input="insertData($event.target.value)" placeholder="Name">
  <input type="password" v-model="userPassword" placeholder="Passwort" id="">
  <input type="email" v-model="userEmail" placeholder="Email">

  <button @click="addUser()">Click</button>
  <div v-if="user.length <= 0">Es gibt keine Users</div>
  <div class="bg-sky-50" v-for="(el, index) in user" :key="index">
    <p>{{ el.name }}</p>
    <h2>{{ el.email }} {{ el.password }}</h2>
  </div>
</template>
<script>


/* import HelloWorld from './components/HelloWorld.vue' */

export default {
  name: 'App',
  components: {
    
  },
  data(){
    return {
      info: "Title", 
      andereTest: "Text",
      user: [],
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
      this.user.push({
        name: this.userName,
        email: this.userEmail,
        password: this.userPassword
      })
    }
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
  margin-top: 60px;
}
</style>

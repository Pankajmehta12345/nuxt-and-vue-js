<script>
import TheWelcome from './TheWelcome.vue';

export default {
  components:
  {
    TheWelcome
  },
  data() {
    return (
      {
        name: '',
        show: false,
        fullName: "",
        values:
        {
          email: '',
          password: ''
        },
        technology: [],
        header: "<h1>my name is: pankaj mehta</h1>",
        hi: 'pankaj',
        test: true,
        btnDisabled: true,
        inputField: true,
        signUp:
        {
          userName: '',
          pass: ''
        },
        error:
        {
          userName: '',
          pass: ''
        }
      }
    )
  },
  props:
  {
    msg: String
  },
  methods:
  {
    hello() {
      this.test = !this.test;
      this.name = 'pankaj';
      this.show = !this.show;
      this.values.email = this.email;
      this.values.password = this.password;
      // console.log("data is: ", this.values);
      // console.log(this.hi)
    },
    updateValue() {
      console.log("hi pankaj mehta")
    },
    signUpUser(e) {
      console.log(this.signUp.userName.length);
      e.preventDefault();
      if (this.signUp.userName.length < 1) {
        this.error.userName = true

      }
      if (this.signUp.pass.length < 1) {
        this.error.pass = true
      }
      else{
        this.error.pass = false;
        this.error.userName = false;
        console.log(this.signUp)
      }
    }
  }

};
</script>

<template>
  <input type="text" v-model="signUp.userName" />
  <p> {{ error.userName ? "username is required":'' }}</p>
  <br />
  <input type="password" v-model="signUp.pass" />
  <p>{{ error.pass ? "password is required":''}}</p>
  <br />
  <button @click="signUpUser">SignUp</button>
  <br />
  <br />
  <br />
  <!-- try -->
  <TheWelcome @changeTitle="updateValue()" />
  <p v-once>{{ test }}</p>
  <p>{{ test }}</p>
  <!-- <div v-bind:style="{backgroundColor:'red',height:'20px',width:'200px'}"></div> -->
  <div class="greetings">
    <p>{{ name }}</p>
    <p>{{ msg }}</p>
    <p v-if="show">{{ show }}</p>
    <!-- <button v-bind:disabled='btnDisabled' v-on:click="hello">Click me</button> -->
    <!-- <button v-on:click="hello">Click me</button> -->
    <button @click="hello">Click me</button>
    <input v-model="fullName" />
    {{ fullName }}
    <p v-show="show">hi pankaj</p>
    <input type="email" v-model="email" />
    <br />
    <input type="password" v-model="password" />
    <br />
    <lable for="technology">
      <input type="checkbox" value="technology" id="abc" v-model="technology" />
      {{ technology }}
      Technology
    </lable>

    <span v-text="msg"></span>
    <!-- <span>{{ msg }}</span> -->
    <p v-html="header"></p>
  </div>
  <!--  -->
</template>

<style scoped>
.greetings {
  color: red;
  /* cursor:not-allowed; */
}
</style>

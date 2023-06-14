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
        inputField: true
      }
    )
  },
  props:
  {
    msg: Number
  },
  methods:
  {
    hello() {
      this.test = !this.test;
      this.name = 'pankaj';
      this.show = !this.show;
      this.values.email = this.email;
      this.values.password = this.password;
      console.log("data is: ", this.values);
      console.log(this.hi)
    },
  }

};
</script>

<template>
  <TheWelcome/>
  <p v-once>{{ test }}</p>
  <p>{{ test }}</p>
  <!-- <div v-bind:style="{backgroundColor:'red',height:'20px',width:'200px'}"></div> -->
  <div class="greetings">
    <p>{{ name }}</p>
    <p>{{ msg }}</p>
    <p v-if="show">{{ show }}</p>
    <!-- <button v-bind:disabled='btnDisabled' v-on:click="hello">Click me</button> -->
    <button v-on:click="hello">Click me</button>
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
</template>

<style scoped>
.greetings {
  color: red;
  /* cursor:not-allowed; */
}

</style>

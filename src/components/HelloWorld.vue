<script>
export default {
  data() {
    return (
      {
        name: '',
        show: false,
        fullName: "",
        values:
        {
          email:'',
          password:''
        }
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
      this.name = 'pankaj';
      this.show = !this.show;
      this.values.email= this.email;
      this.values.password=this.password;
      console.log("data is: ", this.values)
    },
  }

};
</script>

<template>
  <!-- <div v-bind:style="{backgroundColor:'red',height:'20px',width:'200px'}"></div> -->
  <div class="greetings">
    <p>{{ name }}</p>
    <p>{{ msg }}</p>
    <p v-if="show">{{ show }}</p>

    <button v-on:click="hello">Click me</button>
    <input v-model="fullName" />
    {{ fullName }}
    <p v-show="show">hi pankaj</p>
    <input type="email" v-model="email"/>
    <br />
    <input type="password" v-model="password"/>
    <br/>
  </div>
</template>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
}

.greetings {
  color: red;
  /* cursor:not-allowed; */
}

.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {

  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>

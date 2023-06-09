<script>
export default {
  data() {
    return (
      {
        name: 'pankaj',
        show:false
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
      console.log("hi pankaj");
    },
    change(e)
    {
      console.log(e.target.value)
    }

  }
  
};
</script>

<template>
  <div class="greetings">
    <p>{{ name }}</p>
    <p>{{ msg }}</p>
    <p v-if="show">{{ show }}</p>

    <button v-on:click="hello">Click me</button>
    <input v-model="text" v-on:change="change"/>
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

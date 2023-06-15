<script>
export default {
  name: 'TheWelcome',
  methods:
  {
    updateTitle()
    {
      this.$emit('changeTitle')
    }
  }
}
</script>
<template>
  <p>hi pankaj mehta</p>
  <button @click="updateTitle">updateTitle</button>
</template>
    
<template>
  <h1>{{ title }}</h1>
  <p>Testing and learning Vue.js</p>
  <input type="text" ref='name'>
  <button @click="handleClick">click me </button>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      title: "Richard's first Vue app"
    }
  },
  methods: {
    handleClick() {
      console.log(this.$refs.name)
      this.$refs.name.classList.add('active')
      this.$refs.name.focus()
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

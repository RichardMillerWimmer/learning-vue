<template>
  <h1>{{ title }}</h1>
  <p>Testing and learning Vue.js</p>
  <input type="text" ref="name" />
  <button @click="handleClick">click me</button>
  <Popup :header="header" :text="text" theme="sale"/>
</template>

<script>
import Popup from "./components/Popup";

export default {
  name: "App",
  components: {
    Popup,
  },
  data() {
    return {
      title: "Richard's first Vue app",
      header: "This is the prop header",
      text: "text prop for p tag"
    };
  },
  methods: {
    handleClick() {
      console.log(this.$refs.name);
      this.$refs.name.classList.add("active");
      this.$refs.name.focus();
    },
  },
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

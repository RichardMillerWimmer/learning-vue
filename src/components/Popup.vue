<template>
  <div class="backdrop">
    <div class="popup" :class="{ sale: theme === 'sale'}">
      <h1>{{ header }}</h1>
      <p>{{ text }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "Popup",
  props: ["header", "text", "theme"],
};
</script>

<style scoped>
.popup {
  width: 400px;
  padding: 20px;
  margin: 100px auto;
  background: white;
  border-radius: 10px;
}
.backdrop {
  top: 0;
  position: fixed;
  background: rgba(0, 0, 0, 0.5);
  width: 100%;
  height: 100%;
}
h1 {
  color: green;
}
.popup.sale {
    background: red;
    color: white;
}
.popup.sale h1 {
    color: white;
}
</style>
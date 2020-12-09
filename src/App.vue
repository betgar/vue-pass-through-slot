<template>
  <div id="app">
    <Middle>
      <template #strong passthrough>App</template>
    </Middle>
  </div>
</template>

<script>
import Middle from "./components/Middle";

export default {
  name: "App",
  components: {
    Middle,
  },
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

<template>
  <main id="app">
    <MainTipsCalulator />
  </main>
</template>

<script>
import MainTipsCalulator from "./views/MainTipsCalulator.vue";
export default {
  name: "App",
  components: {
    MainTipsCalulator,
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Space Mono", monospace;
}
#app {
  font-family: "Space Mono", monospace;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  display: flex;
  text-align: center;
  justify-content: center;
  height: 100vh;
  background-color: #c5e4e7;
}
@media (max-width: 800px) {
  #app {
    height: 100%;
  }
}
</style>

<template>
  <main id="app">
    <MainView />
  </main>
</template>

<script>
import MainView from "./views/MainView.vue";

export default {
  name: "App",
  components: {
    MainView,
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
#app {
  font-family: "Rubik", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  background-color: hsl(226, 43%, 10%);
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 100vh;
  color: #fff;
}
</style>

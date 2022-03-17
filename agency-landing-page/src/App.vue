<template>
  <main id="app">
    <TopView />
    <MiddleView />
    <PeopleView />
    <BottomView />
  </main>
</template>

<script>
import TopView from "./components/TopView.vue";
import MiddleView from "./components/MiddleView.vue";
import PeopleView from "./components/PeopleView.vue";
import BottomView from "./components/BottomView.vue";
export default {
  name: "App",
  components: {
    TopView,
    MiddleView,
    PeopleView,
    BottomView,
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
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
h1,h2,h3 {
  font-family: "Fraunces", serif;
}
p,span,a {
  font-family: "Outfit", sans-serif;
}
</style>

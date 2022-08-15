<template>
  <main>
    <Calculator />
    <!-- <test /> -->
  </main>
</template>

<script>
import Calculator from "./components/Calculator.vue";
// import test from "./components/test.vue";

export default {
  name: "App",
  components: {
    Calculator,
    // test
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Barlow:wght@900&display=swap");
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Barlow", sans-serif;
  /* background-color: #3b4664; */
}
</style>

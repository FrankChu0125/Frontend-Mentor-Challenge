<template>
  <div class="calculator-app">
    <div class="container">
      <TopView></TopView>
      <ResultArea />

      <div class="controller-btns">
        <div class="normal-btn 7">7</div>
        <div class="normal-btn 8">8</div>
        <div class="normal-btn 9">9</div>
        <div class="normal-btn del">DEL</div>
        <div class="normal-btn 4">4</div>
        <div class="normal-btn 5">5</div>
        <div class="normal-btn 6">6</div>
        <div class="normal-btn +">+</div>
        <div class="normal-btn 1">1</div>
        <div class="normal-btn 2">2</div>
        <div class="normal-btn 3">3</div>
        <div class="normal-btn minus">-</div>
        <div class="normal-btn dot">.</div>
        <div class="normal-btn 0">0</div>
        <div class="normal-btn divide">/</div>
        <div class="normal-btn multi">x</div>
        <div class="footer">
          <div class="middle-btn reset">RESET</div>
          <div class="middle-btn equals">=</div>
        </div>
      </div>

      <div class="footer">
        <p>create by <a>Frank CHU</a></p>
      </div>
    </div>
  </div>
</template>

<script>
import TopView from "./TopView.vue";
import ResultArea from "./ResultArea.vue";
export default {
  name: "calculator-app",
  components: {
    TopView,
    ResultArea,
    // test
  },
  //   data() {},
  //   methods: {},
  //   computed: {},
};
</script>

<style lang="scss">
:root {
  --theme-one-circle: #f56e5b;
  --theme-one-circle-bg: #8c8c8c;

}
.container {
  // width: 800px;
  display: flex;
  justify-content: center;
  flex-direction: column;
  align-items: center;
  // color: #fff;
}
</style>

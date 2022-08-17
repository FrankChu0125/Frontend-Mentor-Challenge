<template>
  <div class="calculator-app">
    <div class="container">
      <TopView></TopView>
      <ResultArea />

      <div class="controller-btns">
        <div class="normal-btn 7"><p>7</p></div>
        <div class="normal-btn 8"><p>8</p></div>
        <div class="normal-btn 9"><p>9</p></div>
        <div class="del"><p>DEL</p></div>

        <div class="normal-btn 4"><p>4</p></div>
        <div class="normal-btn 5"><p>5</p></div>
        <div class="normal-btn 6"><p>6</p></div>
        <div class="normal-btn plus"><p class="mark-sign">+</p></div>

        <div class="normal-btn 1"><p>1</p></div>
        <div class="normal-btn 2"><p>2</p></div>
        <div class="normal-btn 3"><p>3</p></div>
        <div class="normal-btn"><p class="mark-sign">-</p></div>

        <div class="normal-btn dot"><p class="mark-sign">.</p></div>
        <div class="normal-btn 0"><p>0</p></div>
        <div class="normal-btn divide"><p>/</p></div>
        <div class="normal-btn multi"><p>X</p></div>

        <div class="footer">
          <div class="middle-btn reset"><p>RESET</p></div>
          <div class="middle-btn equals"><p>=</p></div>
        </div>
      </div>

      <div class="writer">
        <p>
          create by
          <a href="https://github.com/FrankChu0125" target="_blank"
            >Frank CHU</a
          >
        </p>
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
  --theme1-circle: #d43c2f;
  --theme1-circle-bg: #252d44;
  --theme1-bg: #3b4664;
  --theme1-button-bg: #eae3db;
  --theme1-button-border: #b1a599;
  --theme1-font: #444b5b;
  --theme1-title: #fff;
  --theme1-min-title: #fff;
  --theme1-choise: #fff;
}
.calculator-app {
  background-color: var(--theme1-bg);
}
.container {
  display: flex;
  justify-content: center;
  flex-direction: column;
  align-items: center;
  .controller-btns {
    width: 500px;
    height: 100%;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 20px;
    background-color: #252d44;
    border: 20px solid #252d44;
    border-radius: 15px;
    .normal-btn,
    .middle-btn,
    .del {
      width: 95px;
      height: 50px;
      cursor: pointer;
      border-radius: 8px;
      background-color: hsl(30, 25%, 89%);
      border: 0px solid hsl(28, 16%, 65%);
      color: hsl(221, 14%, 31%);
      border-width: 0px 0px 5px 0px;
      // padding: 5px 15px 5px 15px;
      text-align: center; // 文字水平置中
      > p {
        position: relative;
        top: 50%;
        font-size: 32px;
        // 因為CSS的預設物件都是從左上角靠攏開始，如果沒有調整transform水平和垂直方向都會超過中心
        // translate(x,y) 改變物件的y軸 向上移動一半的距離
        transform: translate(0, -50%);
      }
      .mark-sign {
        font-size: 40px;
      }
    }
    .del {
      background: hsl(225, 21%, 49%);
      // 外框線
      border: 0px solid hsl(224, 28%, 35%);
      border-width: 0px 0px 5px 0px;
      // 字
      color: #fff;
    }

    .footer {
      display: flex;
      width: 500px;
      justify-content: center;
      gap: 20px;
      .middle-btn {
        width: 210px;
        height: 50px;
      }
      .reset,
      .del {
        background: hsl(225, 21%, 49%);
        // 外框線
        border: 0px solid hsl(224, 28%, 35%);
        border-width: 0px 0px 5px 0px;
        // 字
        color: #fff;
      }
      .equals {
        background: hsl(6, 63%, 50%);
        // 外框縣
        border: 0px solid hsl(6, 70%, 34%);
        border-width: 0px 0px 5px 0px;
        // 字
        color: #fff;
      }
    }
  }
  // 按鈕效果
  .controller-btns .normal-btn :hover {
    background: #fff;
    border: 0px solid #fff;
    border-radius: 8px;
    height: 100%;
  }

  .writer {
    padding-top: 20px;
  }
}
.controller-btns .del:hover {
  background: #a2b3e1;
  > p {
    padding-bottom: 8px;
  }
}
.reset :hover {
  background: #a2b3e1;
  border-radius: 8px;
  height: 100%;
}

.equals :hover {
  background: #f96c5b;
  border-radius: 8px;
  height: 100%;
}
</style>

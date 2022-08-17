<template>
  <div class="top">
    <p>calc</p>
    <div class="theme">
      <p class="small-title">THEME</p>
      <div class="selecter">
        <div class="title">1 2 3</div>
        <div class="tabs">
          <input type="radio" id="radio-1" name="tabs" />
          <label class="tab" for="radio-1"></label>
          <input type="radio" id="radio-2" name="tabs" />
          <label class="tab" for="radio-2"></label>
          <input type="radio" id="radio-3" name="tabs" />
          <label class="tab" for="radio-3"></label>
          <!-- 滑在上面的按鈕 -->
          <span class="glider"></span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: top,
};
</script>

<style lang="scss">
.top {
  display: flex;
  width: 500px;
  justify-content: space-between;
  align-items: center;
  p {
    font-size: 20px;
    color: var(--theme1-title);
  }
  .theme {
    display: flex;
    align-items: center;
    gap: 20px;
    .small-title {
      font-size: 10px;
      padding-top: 10px;
      letter-spacing: 2px;
      color: var(--theme1-min-title);
    }
    .selecter {
      .title {
        font-size: 10px;
        padding-left: 8px;
        word-spacing: 11px;
        color: var(--theme1-choise);
      }
      .tabs {
        display: flex;
        position: relative;
        background-color: var(--theme1-circle-bg);
        border-radius: 99px;
        padding: 3px;
        * {
          z-index: 2;
        }
      }
      input[type="radio"] {
        display: none;
      }
      .tab {
        display: flex;
        align-items: center;
        justify-content: center;
        height: 18px;
        width: 18px;
        font-size: 1.25rem;
        font-weight: 500;
        border-radius: 99px;
        cursor: pointer;
        transition: color 0.15s ease-in;
      }
      // 點下的動畫
      input[id="radio-1"] {
        &:checked {
          & ~ .glider {
            transform: translateX(0);
          }
        }
      }
      input[id="radio-2"] {
        &:checked {
          & ~ .glider {
            transform: translateX(100%);
          }
        }
      }
      input[id="radio-3"] {
        &:checked {
          & ~ .glider {
            transform: translateX(200%);
          }
        }
      }
      .glider {
        position: absolute;
        display: flex;
        height: 18px;
        width: 18px;
        background-color: var(--theme1-circle);
        z-index: 1;
        border-radius: 99px;
        transition: 0.25s ease-out;
      }
    }
  }
}
</style>

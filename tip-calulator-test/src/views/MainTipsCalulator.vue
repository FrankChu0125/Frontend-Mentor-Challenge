<template>
  <div class="MainTipsCalulator">
    <div class="title">
      <p>SPLT</p>
      <p>TTER</p>
    </div>
    <div class="container">
      <div class="left">
        <!-- bill  -->
        <div class="inputGroup">
          <h3>Bill</h3>
          <p class="errorBillMsg" v-show="warning">
            Can't be empty or negative
          </p>
        </div>
        <!-- warning -->
        <div class="input">
          <img src="../assets/icon-dollar.svg" alt="dollar" />
          <input
            autocomplete="off"
            type="number"
            name="amount"
            placeholder="0"
            v-model.trim="billInputs"
          />
        </div>
        <!-- select tip -->
        <div class="selectTip">
          <h3>Select Tip %</h3>
          <div class="select-button">
            <input
              v-for="(tip, index) in tips"
              type="button"
              id="normalTips"
              :class="{ active: tip.isActive != tip.isActive }"
              :value="tip.value + '%'"
              :key="index"
              @click="
                {
                  toggleActive(index);
                }
              "
            />
            <input
              type="number"
              class="custom_box"
              placeholder="Custom"
              v-model.trim="customTip"
            />
          </div>
        </div>
        <!-- people -->
        <div class="inputGroup">
          <h3>Number of People</h3>
        </div>
        <div class="input">
          <img src="../assets/icon-person.svg" alt="people-icon" />
          <input
            type="number"
            name="people"
            class="amount-box"
            placeholder="0"
            v-model="peopleInputs"
          />
        </div>
      </div>

      <div class="right">
        <div class="tip-property">
          <div class="info">
            <p class="type">Tip Amount</p>
            <p class="person">/ person</p>
          </div>
          <div class="value">
            <!-- <input
              type="text"
              :value="`$${caluTipAmount}`"
              placeholder="$0.00"
              disabled
            /> -->
            <p>${{ caluTipAmount }}</p>
          </div>
        </div>

        <div class="total">
          <div class="info">
            <p class="type">Total</p>
            <p class="person">/ person</p>
          </div>
          <div class="value">
            <p>${{ caluTotal }}</p>
          </div>
        </div>

        <div class="reset-button" @click="reset">
          <p>RESET</p>
        </div>
      </div>
    </div>
    <p>Create by <a href="https://github.com/FrankChu0125">Frank CHU</a></p>
  </div>
</template>

<script>
export default {
  name: "MainTipsCalulator",
  data() {
    return {
      tips: [
        { value: 5, isActive: false },
        { value: 10, isActive: false },
        { value: 15, isActive: false },
        { value: 25, isActive: false },
        { value: 50, isActive: false },
      ],
      billInputs: null,
      selectTip: 0,
      customTip: 0,
      peopleInputs: null,
      errorPeopleMsg: "",
      tipAmount: 0,
      totalTipsPerson: 0,
      isWarning: false,
    };
  },
  methods: {
    toggleActive(index) {
      this.tips.forEach((tip) => {
        tip.isActive = false;
      });
      this.selectTip = this.tips[index].value;
      this.customTip = null;
      this.tips[index].isActive = !this.tips[index].isActive;
    },
    tipClicked(getInput) {
      this.customTip = null;
      this.selectTip = getInput;
    },
    reset() {
      this.billInputs = null;
      this.selectTip = 0;
      this.customTip = 0;
      this.peopleInputs = null;
      this.tipAmount = 0;
      this.total = 0;
      this.totalTipsPerson = 0;
      this.tips.forEach((tip) => {
        tip.isActive = false;
      });
    },
  },
  computed: {
    warning() {
      return this.billInputs <= 0 ? true : false;
    },
    caluTipAmount() {
      if (this.billInputs < 0 || this.peopleInputs < 0) return;
      let caluTipAmount;
      if (this.billInputs && this.peopleInputs) {
        caluTipAmount = this.customTip
          ? (this.billInputs / this.peopleInputs / 100) * this.customTip
          : (this.billInputs / this.peopleInputs / 100) * this.selectTip;
      } else {
        caluTipAmount = 0;
      }
      return Number.parseFloat(caluTipAmount).toFixed(2);
    },
    caluTotal() {
      if (this.billInputs < 0 || this.peopleInputs < 0) return;
      let calulatTotal;
      if (this.peopleInputs && this.billInputs) {
        calulatTotal = this.billInputs / this.peopleInputs + this.tipAmount;
      } else {
        calulatTotal = 0;
      }
      return Number.parseFloat(calulatTotal).toFixed(2);
    },
  },
};
</script>

<style lang="scss">
input::-webkit-outer-spin-button,
input::-webkit-inner-spin-button {
  -webkit-appearance: none;
  margin: 0;
}

input[type="number"] {
  -moz-appearance: textfield;
}

.MainTipsCalulator {
  display: flex;
  flex-direction: column;
  gap: 50px;
  padding-top: 50px;
  h3 {
    color: hsl(186, 14%, 43%);
  }
  .title {
    p {
      color: hsl(183, 100%, 15%);
      font-size: 20px;
      font-weight: bold;
      letter-spacing: 1.3vh;
    }
  }
  .container {
    display: flex;
    background-color: #fff;
    padding: 30px;
    border-radius: 20px;
    width: 800px;
    gap: 30px;
    .input {
      // display: inline;
      position: relative;
      width: 355px;
      img {
        position: absolute;
        top: 13px;
        left: 10px;
      }
      input {
        width: 100%;
        height: 48px;
        text-align: right;
        font-size: 20px;
        padding-right: 10px;
        background-color: #f3f8fb;
        border: solid 1px #fff;
        border-radius: 5px;
        color: #00474b;
        font-weight: bold;
      }
      // input:hover,
      // input:focus,
      // input:focus-visible {
      //   outline: none;
      //   border: solid 3px hsl(183, 100%, 15%);
      // }
    }
    .left {
      width: 355px;
      .inputGroup {
        display: flex;
        align-items: center;
        justify-content: space-between;
        p {
          color: #e0716d;
        }
      }
      .selectTip {
        margin: 30px 0px;
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        .select-button {
          display: flex;
          flex-wrap: wrap;
          width: 100%;
          gap: 0.8rem;
          padding-top: 1.2rem;
          justify-content: space-between;
          // align-items: center;
          input {
            width: 30.6%;
            height: 2.5rem;
            background-color: hsl(183, 100%, 15%);
            border-radius: 5px;
            color: #f3f8fb;
            border: solid 1px #fff;
            font-size: 20px;
            font-weight: bold;
            text-align: center;
          }
          .custom_box {
            background-color: #f3f8fb;
            color: hsl(183, 100%, 15%);
          }
          #normalTips:focus,
          #normalTips:hover {
            outline: none;
            background-color: #1fc6ac;
            color: hsl(183, 100%, 15%);
          }
        }
      }
    }
    .right {
      width: 355px;
      background-color: hsl(183, 100%, 15%);
      border-radius: 20px;
      color: #fff;
      padding: 25px;
      display: flex;
      flex-direction: column;
      .tip-property,
      .total {
        display: flex;
        justify-content: space-between;
        padding: 15px 0px;
        .type {
          font-size: 19px;
        }
        .person {
          font-size: 10px;
          display: flex;
          padding-top: 5px;
        }
        .value {
          p {
            font-size: 35px;
            color: #1fc6ac;
            font-weight: bold;
          }
        }
      }
      .total {
        padding-bottom: 120px;
      }
      .reset-button {
        background-color: #0d686d;
        display: flex;
        justify-content: center;
        align-items: center;
        height: 40px;
        border-radius: 5px;
        margin-bottom: 5px;
        cursor: pointer;
        p {
          color: hsl(183, 100%, 15%);
          text-align: center;
          font-weight: bold;
          font-size: 22px;
        }
      }
      .reset-button:hover {
        background-color: #24c3ad;
        p {
          color: #0d686d;
        }
      }
    }
  }
}

@media (max-width: 800px) {
  .MainTipsCalulator {
    padding-top: 20px;
    gap: 20px;
    width: 100;
    .container {
      width: 100%;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      .left {
        .selectTip {
          margin: 20px 0px;
        }
      }
      .right {
        .total {
          padding-bottom: 50px;
        }
      }
    }
  }
}
</style>

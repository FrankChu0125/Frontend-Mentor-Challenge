<template>
  <div class="MainView">
    <div class="title">
      <p>SPLT</p>
      <p>TTER</p>
    </div>
    <div class="container">
      <div class="left">
        <!-- bill  -->
        <div class="inputGroup">
          <h3>Bill</h3>
          <p class="errorBillMsg">Can't be empty</p>
        </div>
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
          <div class="button">
            <button class="btn active" id="5" @click="tipClicked(5)">
              <p>5%</p>
            </button>
            <button class="btn" id="10" @click="tipClicked(10)">
              <p>10%</p>
            </button>
            <button class="btn" id="15" @click="tipClicked(15)">
              <p>15%</p>
            </button>
            <button class="btn" id="25" @click="tipClicked(25)">
              <p>25%</p>
            </button>
            <button class="btn" id="50" @click="tipClicked(50)">
              <p>50%</p>
            </button>
            <div class="btn">
              <input
                type="number"
                class="input custom_box"
                placeholder="Custom"
                v-model.trim="selectTip"
              />
            </div>
          </div>
        </div>
        <!-- people -->
        <div class="inputGroup">
          <h3>Number of People</h3>
          <p class="erroPeopleMsg">{{ erroPeopleMsg }}</p>
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
            <p>$0.00</p>
          </div>
        </div>

        <div class="total">
          <div class="info">
            <p class="type">Total</p>
            <p class="person">/ person</p>
          </div>
          <div class="value">
            <p>{{ caluTipAmount }}</p>
          </div>
        </div>

        <div class="reset-button" @click="reset">
          <p>RESET</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "MainView",
  data() {
    return {
      billInputs: 0,
      selectTip: 0,
      peopleInputs: 0,
      erroPeopleMsg: "",
      tipAmount: 0,
      total: 0,
    };
  },
  // update() {
  //   if (!billInputs) {
  //     erroPeopleMsg = "Can't be empty";
  //   }
  //   if (billInputs < 0) {
  //     erroPeopleMsg = "Can't be negative ";
  //   }
  // },
  methods: {
    tipClicked(getInput) {
      this.selectTip = getInput;
    },
    reset() {
      this.billInputs = 0;
      this.selectTip = 0;
      this.peopleInputs = 0;
      this.erroPeopleMsg = "";
    },
  },
  computed: {
    caluTipAmount() {
      if (this.tipAmount !== 0 || this.peopleInputs !== 0) {
        this.tipAmount = 0;

      } else {
        this.tipAmount = 0;
      }
      return this.tipAmount;
      // if (!(amount.value == 0 || people.value == 0)) {
      //   tip_amount = (parseInt(amount.value) * percentage) / 100 / people.value;
      //   total = parseInt(amount.value) + (amount.value * percentage) / 100;
      //   total = total / people.value; // calculate total per person
      // } else {
      //   tip_amount = 0;
      //   total = 0;
      // }
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

.MainView {
  display: flex;
  flex-direction: column;
  gap: 50px;
  padding-top: 80px;
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
      input:hover,
      input:focus {
        outline: none;
        border: solid 3px hsl(183, 100%, 15%);
      }
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
        .button {
          display: flex;
          flex-flow: wrap;
          width: 355px;
          gap: 10px;
          padding: 10px 0px;
          .btn {
            height: 45px;
            width: 111px;
            background-color: hsl(183, 100%, 15%);
            border-radius: 5px;
            border: 0px;
            cursor: pointer;
            input {
              width: 100%;
              height: 100%;
              text-align: center;
              border-radius: 5px;
              outline: none;
              border: 2px solid #f3f8fb;
              background-color: #f3f8fb;
              font-size: 20px;
              font-weight: bold;
              color: hsl(183, 100%, 15%);
            }
            input:hover {
              outline: none;
              border: 3px solid hsl(183, 100%, 15%);
            }
            p {
              color: #fff;
              font-size: 20px;
              font-weight: bold;
            }
          }
          .btn:hover {
            background-color: #24c3ad;
            p {
              color: hsl(183, 100%, 15%);
            }
          }
          .btn:ti {
            background-color: #24c3ad;
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
  .MainView {
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
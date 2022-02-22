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
          />
        </div>
        <!-- select tip -->
        <div class="selectTip">
          <h3>Select Tip %</h3>
          <div class="button">
            <button class="btn active" id="5" onclick="tipclicked(this)">
              <p>5%</p>
            </button>
            <button class="btn" id="10" onclick="tipclicked(this)">
              <p>10%</p>
            </button>
            <button class="btn" id="15" onclick="tipclicked(this)">
              <p>15%</p>
            </button>
            <button class="btn" id="25" onclick="tipclicked(this)">
              <p>25%</p>
            </button>
            <button class="btn" id="50" onclick="tipclicked(this)">
              <p>50%</p>
            </button>
            <button class="btn" id="custom">
              <p>custom</p>
              <!-- <input
                type="number"
                class="hide custom_box"
                placeholder="0"
                oninput="formSelect(this)"
              /> -->
            </button>
          </div>
        </div>
        <!-- people -->
        <div class="inputGroup">
          <h3>Number of People</h3>
          <p class="erroPeopleMsg">Can't be zero</p>
        </div>
        <div class="input">
          <img src="../assets/icon-person.svg" alt="people-icon" />
          <input
            type="number"
            name="people"
            class="amount-box"
            placeholder="0"
            oninput="formChange(this)"
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
            <p>$0.00</p>
          </div>
        </div>

        <div class="reset-button">
          <p>RESET</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "MainView",
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
        background-color: #c5e4e7;
        border: solid 1px #fff;
        border-radius: 5px;
        color: #00474b;
        font-weight: bold;
      }
      input:hover,
      input:focus {
        outline: none;
        border: solid 3px hsl(172, 67%, 45%);
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
            p {
              color: #fff;
              font-size: 20px;
              font-weight: bold;
            }
          }
          .btn:hover {
            background-color: #9fe8df;
            p {
              color: hsl(183, 100%, 15%);
            }
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
        background-color: #9fe8df;
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
        background-color: #fff;
        p {
          color: #1fc6ac;
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
<template>
  <div class="topView">
    <header>
      <div class="nav">
        <div class="logo">
          <h2>sunnyside</h2>
        </div>
        <div class="menu">
          <ul class="list">
            <li><a class="item"> About</a></li>
            <li><a class="item">Services</a></li>
            <li><a class="item">Projects</a></li>
            <li><a class="item">CONTACT</a></li>
          </ul>
        </div>
      </div>
      <div class="title">
        <div class="word"><h1>WE ARE CREATIVES</h1></div>
        <div class="arrow-down">
          <img src="../assets/icon-arrow-down.svg" alt="" />
        </div>
      </div>
    </header>
  </div>
</template>

<script>
export default {
  name: "TopView",
};
</script>

<style lang="scss">
.topView {
  header {
    background-image: url("../assets/image-header.jpg");
    background-repeat: no-repeat;
    background-size: cover;
    background-position: center;
    width: 100%;
    height: 800px;
    color: #fff;
    .nav {
      display: flex;
      width: 100%;
      justify-content: space-between;
      padding: 30px 10px 0px 10px;
      .logo {
        font-weight: bold;
        h2 {
          position: absolute;
          top: 25px;
        }
      }
      .menu ul {
        list-style: none;
        display: flex;
        li a {
          padding: 18px;
          font-size: 15px;
          cursor: default;
        }
        a:hover {
          background-color: rgba(255, 255, 255, 0.315);
          border-radius: 30px;
          cursor: pointer;
        }
      }
    }
    .title {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      padding-top: 100px;
      .word {
        font-size: 30px;
        padding-bottom: 80px;
        font-weight: bold;
        text-align: center;
      }
      .arrow-down {
        width: 20px;
        padding-top: 30px;
        img {
          cursor: pointer;
        }
      }
    }
  }
}
</style>
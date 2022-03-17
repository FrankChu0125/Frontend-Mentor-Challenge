<template>
  <div class="BottomView">
    <div class="imgCard">
      <img src="../assets/image-gallery-milkbottles.jpg" alt="milkbottles" />
      <img src="../assets/image-gallery-orange.jpg" alt="orange" />
      <img src="../assets/image-gallery-cone.jpg" alt="cone" />
      <img src="../assets/image-gallery-sugarcubes.jpg" alt="sugetcubes" />
    </div>
    <div class="sunnyside">
      <h3>sunnyside</h3>
      <div class="info">
        <a>About</a>
        <a>Services</a>
        <a>Projects</a>
      </div>
      <div class="logo">
        <img src="../assets/icon-facebook.svg" alt="fb" />
        <img src="../assets/icon-instagram.svg" alt="ig" />
        <img src="../assets/icon-twitter.svg" alt="tw" />
        <img src="../assets/icon-pinterest.svg" alt="pinterest" />
      </div>
      <div class="creator">
        <p>
          Coded by
          <a href="https://github.com/FrankChu0125" target="_blank"
            >Frank Chu</a
          >
          .
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "BottomView",
};
</script>

<style lang="scss">
.BottomView {
  background-color: #90d4c5;
  .imgCard {
    font-size: 0;
    display: flex;
    width: 100%;
    img {
      width: 25%;
    }
  }
  .sunnyside {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding: 50px 0px;
    color: #2d7464;
    cursor: default;
    h3 {
      font-family: "Barlow", sans-serif;
      font-weight: 1000;
      font-size: 21px;
    }
    .info {
      display: flex;
      justify-content: space-around;
      padding: 40px 0px;
      a {
        padding: 0px 30px;
      }
      a:hover {
        color: #fff;
        cursor: pointer;
      }
    }
    .logo {
      padding-top: 30px;
      img {
        padding: 0px 20px;
      }
      img:hover {
        filter: invert(1);
        cursor: pointer;
      }
    }
    .creator {
      margin-top: 40px;
    }
  }
}
</style>
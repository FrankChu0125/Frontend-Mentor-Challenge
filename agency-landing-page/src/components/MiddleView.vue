<template>
  <div class="middleView">
    <div class="wrap">
      <div class="content-text">
        <div class="text">
          <h3>Transform your brand</h3>
          <p>
            We are a full-service creative agency specializing in helping brands
            grow fast. Engage your clients through compelling visuals that do
            most of the marketing for you.
          </p>
          <h4 class="learn-yellow">LEARN MORE</h4>
        </div>
      </div>
      <div class="content-img">
        <img src="../assets/image-transform.jpg" />
      </div>
    </div>
    <div class="wrap">
      <div class="content-img">
        <img src="../assets/image-stand-out.jpg" />
      </div>
      <div class="content-text">
        <div class="text">
          <h3>Stand out to the right audience</h3>
          <p>
            Using a collaborative formula of designers, researchers,
            photographers, videographers, and copywriters, we’ll build and
            extend your brand in digital places.
          </p>
          <h4 class="learn-red">LEARN MORE</h4>
        </div>
      </div>
    </div>
    <div class="wrap">
      <div class="content-design">
        <!-- <img src="../assets/image-graphic-design.jpg" /> -->
        <div class="text">
          <h3>Graphic design</h3>
          <p>
            Great design makes you memorable. We deliver artwork that
            underscores your brand message and captures potential clients’
            attention.
          </p>
        </div>
      </div>
      <div class="content-design photo">
        <!-- <img src="../assets/image-photography.jpg" /> -->
        <div class="text">
          <h3>Photography</h3>
          <p>
            Increase your credibility by getting the most stunning, high-quality
            photos that improve your business image.
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "MiddleView",
};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Fraunces:wght@900&display=swap");
.middleView {
  .wrap {
    display: flex;
    width: 100%;
    .content-text {
      width: 50%;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      .text {
        width: 500px;
        color: #2e3844;
        h3 {
          font-family: "Fraunces", serif;
          font-size: 45px;
        }
        p {
          padding: 50px 0px;
          font-size: 15px;
          width: 400px;
          letter-spacing: 0.01vmin;
          line-height: 1.5rem;
        }
        h4 {
          position: relative;
          display: block;
          cursor: default;
          &::before {
            content: ""; //注意無論如何都要有content，偽元素才能正確顯示
            position: absolute;
            width: 114px;
            height: 7px;
            background-color: hsl(51, 100%, 49%);
            bottom: 0px;
            opacity: 0.8;
            left: -2px;
            border-radius: 5px;
            z-index: -1;
            cursor: pointer;
          }
          &:hover::before {
            height: 100%;
          }
        }
        .learn-red {
          &::before {
            background-color: hsl(7, 99%, 70%);
          }
        }
      }
    }
    .content-img {
      width: 50%;
      font-size: 0;
      img {
        width: 100%;
      }
    }
    .content-design {
      background-image: url("../assets/image-graphic-design.jpg");
      background-size: cover;
      width: 50%;
      .text {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        text-align: center;
        padding-top: 350px;
        color: #1b5972da;
        h3 {
          font-size: 23px;
        }
        p {
          width: 380px;
          line-height: 25px;
          padding: 20px 0px;
          font-weight: 600;
        }
      }
    }
    .photo {
      background-image: url("../assets/image-photography.jpg");
    }
  }
}
</style>
<template>
  <div class="PeopleView">
    <div class="title">
      <h2>CLIENT TESTIMONIALS</h2>
    </div>
    <div class="list">
      <div class="card">
        <div class="photo">
          <img src="../assets/image-emily.jpg" alt="emily" />
        </div>
        <div class="info">
          <span>
            We put our trust in Sunnyside and they delivered, making sure our
            needs were met and deadlines were always hit.
          </span>
          <div class="self">
            <h3>Emily R.</h3>
            <p>Marketing Director</p>
          </div>
        </div>
      </div>

      <div class="card">
        <div class="photo">
          <img src="../assets/image-thomas.jpg" alt="thomas" />
        </div>
        <div class="info">
          <span>
            Sunnyside’s enthusiasm coupled with their keen interest in our
            brand’s success made it a satisfying and enjoyable experience.
          </span>
          <div class="self">
            <h3>Thomas S.</h3>
            <p>Chief Operating Officer</p>
          </div>
        </div>
      </div>

      <div class="card">
        <div class="photo">
          <img src="../assets/image-jennie.jpg" alt="jennie" />
        </div>
        <div class="info">
          <span>
            Incredible end result! Our sales increased over 400% when we worked
            with Sunnyside. Highly recommended!
          </span>
          <div class="self">
            <h3>Jennie F.</h3>
            <p>Business Owner</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "PeopleView",
};
</script>

<style lang="scss">
.PeopleView {
  display: flex;
  flex-direction: column;
  align-items: center;
  .title {
    padding: 8em 0px 2em 0px;
    h2 {
      color: hsl(232, 10%, 55%);
      letter-spacing: 0.25em;
    }
  }
  .list {
    display: flex;
    padding-bottom: 8em;
    .card {
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      padding: 0px 28px;
      .photo {
        padding: 40px;
        img {
          width: 72px;
          border-radius: 36px;
        }
      }
      .info {
        display: flex;
        flex-direction: column;
        span {
          font-size: 16px;
          text-align: center;
          letter-spacing: 2px;
          line-height: 2rem;
          padding: 10px 20px 50px 20px;
        }
        .self {
          display: flex;
          flex-direction: column;
          justify-content: center;
          align-items: center;
          h3 {
            font-size: 20px;
            padding-bottom: 15px;
          }
          p {
            color: hsl(232, 10%, 55%);
          }
        }
      }
    }
  }
}
</style>
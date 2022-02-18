<template>
  <div class="mainView">
    <div class="myself-card">
      <div class="myself-card_head">
        <img src="../assets/image-jeremy.png" alt="Jeremy Robson" />
        <div class="Robson">
          <p>Report for</p>
          <h2>Jeremy</h2>
          <h2>Robson</h2>
        </div>
      </div>
      <div class="myself-card_footer">
        <ul class="myself-card_times">
          <li class="myself-card_list">
            <a class="daily" @click.stop="getChange" href="#">Daily</a>
          </li>
          <li class="myself-card_list">
            <a class="weekly" @click.stop="getChange" href="#">Weekly</a>
          </li>
          <li class="myself-card_list">
            <a class="monthly" @click.stop="getChange" href="#"> Monthly </a>
          </li>
        </ul>
      </div>
    </div>
    <WorkCard :nowClick="nowClick" />
  </div>
</template>

<script>
import WorkCard from "../components/WorkCard.vue";
export default {
  name: "MainView",
  components: {
    WorkCard,
  },
  data() {
    return {
      nowClick: "daily",
    };
  },
  methods: {
    getChange(event) {
      this.nowClick = event.target.className;
    },
  },
};
</script>

<style lang="scss">
.mainView {
  display: flex;
}
.myself-card {
  display: flex;
  flex-direction: column;
  background-color: hsl(235, 46%, 20%);
  border-radius: 10px;
}
.myself-card_head {
  background-color: hsl(246, 80%, 60%);
  // hsl(246, 80%, 60%)
  display: flex;
  flex-direction: column;
  padding: 30px;
  border-radius: 10px;
  img {
    width: 50px;
    border: 2.5px solid #fff;
    border-radius: 28px;
  }
  .Robson {
    padding: 25px 0px 80px 0px;
    p {
      font-weight: 200;
      font-size: 0.8rem;
    }
    h2 {
      font-size: 2rem;
      font-weight: 500;
      padding: 0px 25px 0px 0px;
      letter-spacing: 1.8px;
    }
  }
}
.myself-card_footer {
  ul {
    list-style: none;
    padding: 40px 0px 20px 0px;
    li {
      display: flex;
      padding: 10px 30px;
      a {
        text-decoration: none;
        color: hsl(235, 45%, 61%);
        cursor: pointer;
      }
      a:hover {
        color: #fff;
      }
    }
  }
}
</style>
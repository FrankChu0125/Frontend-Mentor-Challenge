<template>
  <div class="WorkCard">
    <!-- work -->
    <div class="workCard time-used-card">
      <div class="cardTop head-card">
        <img src="../assets/icon-work.svg" alt="work-icon" />
      </div>
      <div class="content-card">
        <div class="title">
          <p class="type">Work</p>
          <img src="../assets/icon-ellipsis.svg" alt="ellipsis" />
        </div>
        <div class="info">
          <p class="title">{{ this[nowClick]["Work"].used }}hrs</p>
          <p>Last week - {{ this[nowClick]["Work"].last }}hrs</p>
        </div>
      </div>
    </div>
    <!-- play -->
    <div class="playCard time-used-card">
      <div class="cardTop head-card">
        <img src="../assets/icon-play.svg" alt="work-icon" />
      </div>
      <div class="content-card">
        <div class="title">
          <p class="type">Play</p>
          <img src="../assets/icon-ellipsis.svg" alt="ellipsis" />
        </div>
        <div class="info">
          <p class="title">{{ this[nowClick]["Play"].used }}hrs</p>
          <p>Last week - {{ this[nowClick]["Play"].last }}hrs</p>
        </div>
      </div>
    </div>
    <!-- study -->
    <div class="studyCard time-used-card">
      <div class="cardTop head-card">
        <img src="../assets/icon-study.svg" alt="work-icon" />
      </div>
      <div class="content-card">
        <div class="title">
          <p class="type">Study</p>
          <img src="../assets/icon-ellipsis.svg" alt="ellipsis" />
        </div>
        <div class="info">
          <p class="title">{{ this[nowClick]["Study"].used }}hrs</p>
          <p>Last week - {{ this[nowClick]["Study"].last }}hrs</p>
        </div>
      </div>
    </div>
    <!-- exercise -->
    <div class="exerciseCard time-used-card">
      <div class="cardTop head-card">
        <img src="../assets/icon-exercise.svg" alt="work-icon" />
      </div>
      <div class="content-card">
        <div class="title">
          <p class="type">Exercise</p>
          <img src="../assets/icon-ellipsis.svg" alt="ellipsis" />
        </div>
        <div class="info">
          <p class="title">{{ this[nowClick]["Exercise"].used }}hrs</p>
          <p>Last week - {{ this[nowClick]["Exercise"].last }}hrs</p>
        </div>
      </div>
    </div>
    <!-- social -->
    <div class="socialCard time-used-card">
      <div class="cardTop head-card">
        <img src="../assets/icon-social.svg" alt="work-icon" />
      </div>
      <div class="content-card">
        <div class="title">
          <p class="type">Social</p>
          <img src="../assets/icon-ellipsis.svg" alt="ellipsis" />
        </div>
        <div class="info">
          <p class="title">{{ this[nowClick]["Social"].used }}hrs</p>
          <p>Last week - {{ this[nowClick]["Social"].last }}hrs</p>
        </div>
      </div>
    </div>
    <!-- self care -->
    <div class="selfCareCard time-used-card">
      <div class="cardTop head-card">
        <img src="../assets/icon-self-care.svg" alt="work-icon" />
      </div>
      <div class="content-card">
        <div class="title">
          <p class="type">Self Care</p>
          <img src="../assets/icon-ellipsis.svg" alt="ellipsis" />
        </div>
        <div class="info">
          <p class="title">{{ this[nowClick]["SelfCare"].used }}hrs</p>
          <p>Last week - {{ this[nowClick]["SelfCare"].last }}hrs</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "WorkCard",
  props: ["nowClick"],
  data() {
    return {
      daily: {
        Work: {
          used: 0,
          last: 0,
        },
        Play: {
          used: 0,
          last: 0,
        },
        Study: {
          used: 0,
          last: 0,
        },
        Exercise: {
          used: 0,
          last: 0,
        },
        Social: {
          used: 0,
          last: 0,
        },
        SelfCare: {
          used: 0,
          last: 0,
        },
      },
      weekly: {
        Work: {
          used: 0,
          last: 0,
        },
        Play: {
          used: 0,
          last: 0,
        },
        Study: {
          used: 0,
          last: 0,
        },
        Exercise: {
          used: 0,
          last: 0,
        },
        Social: {
          used: 0,
          last: 0,
        },
        SelfCare: {
          used: 0,
          last: 0,
        },
      },
      monthly: {
        Work: {
          used: 0,
          last: 0,
        },
        Play: {
          used: 0,
          last: 0,
        },
        Study: {
          used: 0,
          last: 0,
        },
        Exercise: {
          used: 0,
          last: 0,
        },
        Social: {
          used: 0,
          last: 0,
        },
        SelfCare: {
          used: 0,
          last: 0,
        },
      },
    };
  },

  mounted() {
    axios.get("https://api.npoint.io/c9851b19c11badba0238").then((res) => {
      res.data.forEach(({ daily, weekly, monthly }) => {
        if (daily) this.daily = daily;
        if (weekly) this.weekly = weekly;
        if (monthly) this.monthly = monthly;
      });
    });
  },
};
</script>

<style lang="scss">
.WorkCard {
  padding-left: 30px;
  display: flex;
  flex-wrap: wrap;
  width: 780px;
  gap: 20px;
  .workCard {
    background-color: hsl(15, 100%, 70%);
  }
  .playCard {
    background-color: hsl(195, 74%, 62%);
  }
  .studyCard {
    background-color: hsl(348, 100%, 68%);
  }
  .exerciseCard {
    background-color: hsl(145, 58%, 55%);
  }
  .socialCard {
    background-color: hsl(264, 64%, 52%);
  }
  .selfCareCard {
    background-color: hsl(43, 84%, 65%);
  }
  .time-used-card {
    border-radius: 1rem;
    width: 230px;
    .head-card {
      text-align: end;
      max-height: 50px;
      overflow: hidden;
      padding-right: 1rem;
    }
    .content-card:hover {
      background-color: hsl(236, 41%, 34%);
    }
    .content-card {
      padding: 25px;
      background-color: hsl(235, 46%, 20%);
      border-radius: 1rem;
      .title {
        display: flex;
        justify-content: space-between;
        align-items: center;
        width: 100%;
        padding-bottom: 20px;
        p {
          font-size: 18px;
          color: #fff;
        }
        img {
          height: 5px;
          cursor: pointer;
        }
      }
      .info {
        .title {
          font-size: 2.5rem;
          font-weight: 200;
          padding-bottom: 10px;
          color: #fff;
        }
        > p {
          font-size: 0.5rem;
          color: hsl(236, 100%, 87%);
          padding-bottom: 30px;
        }
      }
    }
  }
}
@media (min-width: 980px) {
  .workCard {
    display: block;
    width: 100%;
  }
}
</style>
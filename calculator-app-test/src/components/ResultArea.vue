<template>
  <div class="result-area">
    <p>50,000</p>
  </div>
</template>

<script>
export default {
  name: "ResultArea",
};
</script>

<style lang="scss">
.result-area {
  margin: 30px 0px;
  padding: 0px 20px;
  width: 500px;
  height: 140px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: end;
  background-color: #181f32;
  border-radius: 15px;
  p {
    align-items: end;
    color: #fff;
    font-size: 60px;
  }
}
</style>

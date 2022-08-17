<template>
  <div class="button">CLICK</div>
  <!-- stylesheet for this button -->
</template>

<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "test",
};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600&display=swap");

:root {
  --primary-color: #185ee0;
  --secondary-color: #e6eef9;
}

.button {
  cursor: pointer;
  display: inline-block;
  white-space: nowrap;
  background: #eae3db;
  border-radius: 8px;
  border: 0px solid #b1a599;
  border-width: 0px 0px 5px 0px;
  padding: 5px 15px 5px 15px;
  color: #444b5b;
}

</style>

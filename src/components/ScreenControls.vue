<template>
  <div>
    <h2 class="title">Screens <img src="../assets/desktop.svg" /></h2>
    <div class="controls">
      <ScreensOption left="work" right="work" />
      <ScreensOption left="personal" right="personal" />
    </div>
    <div class="controls">
      <ScreensOption left="work" right="personal" />
      <ScreensOption left="personal" right="work" />
    </div>
  </div>
</template>

<script lang="ts">
import Vue from "vue";
import ScreensOption from "./ScreensOption.vue";

export default Vue.extend({
  name: "ScreenControls",
  components: {
    ScreensOption
  }
});
</script>

<style scoped lang="scss">
@import "../theme.scss";
.title {
  font-weight: normal;
  display: flex;
  align-items: center;
  img {
    height: 28px;
    margin-bottom: -3px;
    margin-left: 8px;
  }
}
.controls {
  display: flex;
  margin-bottom: 64px;
}
.controls > div:first-child {
  margin-right: 32px;
}
.controls > div:last-child {
  margin-left: 32px;
}
</style>

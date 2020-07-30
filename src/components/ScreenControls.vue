<template>
  <div>
    <h2 class="title">Screens <img src="../assets/desktop.svg" /></h2>
    <div class="controls">
      <ScreensOption
        v-for="(option, index) in options"
        :key="index"
        :left="option[0]"
        :right="option[1]"
        :active="active === index"
        @click.native="switchTo(index)"
      />
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
  },
  data() {
    return {
      options: [
        ["work", "work"],
        ["personal", "personal"],
        ["work", "personal"],
        ["personal", "work"]
      ],
      active: 0
    };
  },
  methods: {
    switchTo(index: number) {
      this.active = index;
    }
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
    height: 26px;
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

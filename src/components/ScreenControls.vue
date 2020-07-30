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
        :click="() => switchTo(index)"
      />
    </div>
  </div>
</template>

<script lang="ts">
import Vue from "vue";
import ScreensOption from "./ScreensOption.vue";
import Machines from "../Machines";

export default Vue.extend({
  name: "ScreenControls",
  components: {
    ScreensOption
  },
  data() {
    return {
      options: [
        [Machines.work, Machines.work],
        [Machines.personal, Machines.personal],
        [Machines.work, Machines.personal],
        [Machines.personal, Machines.work]
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

$margin: 32px;

.title {
  margin-left: $margin;
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
  flex-wrap: wrap;
}
.controls > div {
  margin: 0 $margin (2 * $margin) $margin;
}
</style>

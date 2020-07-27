<template>
  <div class="root">
    <div class="left">
      {{ Machines[left].label }}
    </div>
    <div class="divider"></div>
    <div class="right">{{ Machines[right].label }}</div>
  </div>
</template>

<script lang="ts">
import Vue from "vue";

const Machines = {
  work: {
    label: "W"
  },
  personal: {
    label: "P"
  }
};

export default Vue.extend({
  name: "ScreensOption",
  props: ["left", "right"],
  data() {
    return {
      Machines
    };
  }
});
</script>

<style scoped lang="scss">
@import "../theme.scss";

$width: 384px;
$height: $width / 2;

.root {
  width: $width;
  height: $height;
  display: flex;
  cursor: pointer;
}

.left,
.right {
  width: $width / 2;
  background: $bg-control;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 32px;
}

.left {
  border-top-left-radius: $border-radius;
  border-bottom-left-radius: $border-radius;
}

.right {
  border-top-right-radius: $border-radius;
  border-bottom-right-radius: $border-radius;
}

.divider {
  width: 1px;
}
</style>

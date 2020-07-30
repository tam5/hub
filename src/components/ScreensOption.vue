<template>
  <div class="root" :class="{ active, disabled }" v-on:click="handleClick">
    <div class="left">
      {{ left.label }}
    </div>
    <div class="divider"></div>
    <div class="right">{{ right.label }}</div>
  </div>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "ScreensOption",
  props: ["left", "right", "active", "click"],
  methods: {
    handleClick() {
      if (!this.disabled) {
        this.click();
      }
    }
  },
  computed: {
    disabled() {
      return !(this.left.available && this.right.available);
    }
  }
});
</script>

<style scoped lang="scss">
@import "../theme.scss";

$width: 384px;
$height: $width / 2;
$border-width: 1px;

.root {
  width: $width;
  height: $height;
  display: flex;
  cursor: pointer;
  position: relative;
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
  width: 2px;
  background: $bg-app;
}

.active {
  display: -webkit-box;
  display: flex;
  -webkit-box-align: center;
  position: relative;
  background-clip: padding-box;
  border: solid $border-width transparent;
  border-radius: $border-radius;

  &:before {
    content: "";
    position: absolute;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    z-index: -1;
    margin: -$border-width;
    border-radius: inherit;
    @include gradient1;
  }
}

.disabled {
  cursor: not-allowed;

  .left,
  .right {
    background: darken($bg-app, 1%);
    color: darken($text-color-primary, 30%);
  }
}
</style>

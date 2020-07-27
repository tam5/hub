<template>
  <div class="root" :class="{ active }">
    <div class="left">
      {{ Machines[left].label }}
    </div>
    <div class="divider"></div>
    <div class="right">{{ Machines[right].label }}</div>
    <div class="module-border-wrap"><div class="module">
Lorem ipsum dolor sit amet consectetur adipisicing elit. Vero pariatur corporis quaerat voluptatum eos tempora temporibus nisi voluptates sed, exercitationem sequi dolore culpa incidunt accusamus, quasi unde reprehenderit ea molestias.
</div></div>
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
  props: ["left", "right", "active"],
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

.module-border-wrap {
  max-width: 250px;
  padding: 1rem;
  position: relative;
  background: linear-gradient(to right, red, purple);
  padding: 3px;
}

.module {
  background: #222;
  color: white;
  padding: 2rem;
}

.root {
  width: $width;
  height: $height;
  display: flex;
  cursor: pointer;
}

.active {
    border: 1px solid orange;
    background-clip: padding-box;
    position: relative;
    box-sizing: border-box;

    &:before {
        content: '';
        position: absolute;
        top: 0;
        right: 0;
        bottom: 0;
        left: 0;
        z-index: -1;
        margin: -1px;
        border-radius: inherit;
        background: linear-gradient(to right, red, orange);

    }
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

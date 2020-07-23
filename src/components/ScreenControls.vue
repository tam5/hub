<template>
  <div>
    <h2>Screens</h2>
    <ScreensOption left="work" right="work" />
    <ScreensOption left="personal" right="personal" />
    <ScreensOption left="work" right="personal" />
    <ScreensOption left="personal" right="work" />
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

<style scoped lang="scss"></style>

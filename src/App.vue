<template>
  <div id="app">
    <ScreenControls />
  </div>
</template>

<script lang="ts">
import Vue from "vue";
import ScreenControls from "./components/ScreenControls.vue";

export default Vue.extend({
  name: "App",
  components: {
    ScreenControls
  }
});
</script>

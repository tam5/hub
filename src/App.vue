<template>
  <div id="app">
    <div class="container">
      <ScreenControls />
    </div>
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

<style lang="scss">
@import "theme.scss";
@import url("https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap");

html,
body,
#app {
  height: 100%;
  width: 100%;
  margin: 0;
  padding: 0;
  font-family: "Montserrat", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

body {
  background: $bg-app;
}

#app {
  display: flex;
  justify-content: center;
  color: $text-color-primary;
}

.container {
  width: 1080px;
}
</style>

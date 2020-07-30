<template>
  <div class="gradient-box">
    <p>
      Lorem ipsum dolor sit amet, consectetur adipiscing elit. Praesent
      bibendum, lorem vel tincidunt imperdiet, nibh elit laoreet felis, a
      bibendum nisl tortor non orci. Donec pretium fermentum felis, quis aliquet
      est rutrum ut. Integer quis massa ut lacus viverra pharetra in eu lacus.
      Aliquam tempus odio adipiscing diam pellentesque rhoncus. Curabitur a
      bibendum est.
    </p>
  </div>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "Example"
});
</script>

<style scoped lang="scss">
.gradient-box {
  display: -webkit-box;
  display: flex;
  -webkit-box-align: center;
  align-items: center;
  width: 90%;
  margin: auto;
  max-width: 22em;
  position: relative;
  padding: 30% 2em;
  box-sizing: border-box;
  color: #fff;
  background: #000;
  background-clip: padding-box;
  border: solid 5px transparent;
  border-radius: 1em;
}
.gradient-box:before {
  content: "";
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: -1;
  margin: -5px;
  border-radius: inherit;
  background: -webkit-gradient(
    linear,
    left top,
    right top,
    from(red),
    to(orange)
  );
  background: linear-gradient(to right, red, orange);
}
</style>

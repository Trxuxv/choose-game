<template>
  <div class="h-screen w-full bg-yellow-100 flex items-center justify-center body">
    <NuxtChild />
  </div>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "Initialization",
});
</script>
<style>
@font-face {
  font-family: "JetBrains";
  src: url("./../static/fonts/JetBrainsMonoNL-Regular.ttf") format("truetype");
}

@keyframes blinker {
  50% {
    opacity: 0;
  }
}

* {
  font-family: "JetBrains";
}
</style>

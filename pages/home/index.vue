<template>
  <div class="h-screen w-full bg-yellow-100 flex items-center justify-center body">
    <div class="bg-white shadow-2xl w-4/6 h-4/6 rounded-lg flex items-center justify-center">
      <div class="text-2xl w-3/6 text-center">
        Enter your name:
        <input type="text" class=" mt-2
        form-control
        block
        w-full
        px-3
        py-1.5
        text-base
        font-normal
        text-gray-700
        bg-white bg-clip-padding
        border border-solid border-gray-300
        rounded
        transition
        ease-in-out
        m-0
        focus:text-gray-700 focus:bg-white focus:border-yellow-600 focus:outline-none
      " id="exampleFormControlInput1" placeholder="Ex. Katy Perry" />
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: "Home",
})
</script>
<style>
@font-face {
  font-family: "JetBrains";
  src: url('./../../static/fonts/JetBrainsMonoNL-Regular.ttf') format("truetype");
}

@keyframes blinker {
  50% {
    opacity: 0;
  }
}

.body {
  font-family: 'JetBrains';
}
</style>

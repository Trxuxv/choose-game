<template>
  <div class="h-screen w-full bg-yellow-100 flex items-center justify-center body">
    <div class="bg-white shadow-2xl w-4/6 h-4/6 rounded-lg flex items-center justify-center">
      <div class="text-2xl font-bold w-3/6 text-center">
        Enter your name:
        <input type="text" class=" mt-4
        form-control
        block
        text-yellow-600
        mx-auto
        w-5/6
        px-3
        py-1.5
        text-base
        font-bold
        bg-white bg-clip-padding
        border border-solid border-gray-300
        rounded
        transition
        ease-in-out
        m-0
        focus:text-yellow-800 focus:font-bold focus:bg-white focus:border-yellow-600 focus:outline-none
      " id="exampleFormControlInput1" placeholder="Ex. Katy Perry" />
        <button type="button" data-mdb-ripple="true" data-mdb-ripple-color="light"
          class="inline-block px-6 mt-4 py-2.5 bg-yellow-600 w-5/6 text-white font-medium text-xs leading-tight uppercase rounded shadow-md hover:bg-yellow-700 hover:shadow-lg focus:bg-yellow-700 focus:shadow-lg focus:outline-none focus:ring-0 active:bg-blue-800 active:shadow-lg transition duration-150 ease-in-out">Click
          me</button>
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

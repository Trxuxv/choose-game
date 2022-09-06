<template>
    <div
      class="bg-white shadow-2xl w-4/6 h-4/6 rounded-lg flex items-center justify-center"
    >
     2
    </div>
  </template>
  
  <script lang="ts">
  import Vue from "vue";
  
  export default Vue.extend({
    name: "Home",
    data() {
      return {
        playerName: "",
      };
    },
    methods: {
      start() {
        alert(this.playerName);
      },
    },
  });
  </script>
  <style>
  @font-face {
    font-family: "JetBrains";
    src: url("./../../../static/fonts/JetBrainsMonoNL-Regular.ttf") format("truetype");
  }
  
  @keyframes blinker {
    50% {
      opacity: 0;
    }
  }
  
  .body {
    font-family: "JetBrains";
  }
  </style>
  
<template>
  <div
    class="body shadow-2xl w-3/6 h-4/6 rounded-lg flex items-center justify-center z-0"
  >
    <div id="container" class="flex w-full h-full flex-col rounded-lg shadow-2xl">
      <div class="w-full h-12 shadow-md z-10 pb-1">
        <div class="dots-bars-3 mt-4 ml-4 float-left"></div>
        <div class="mt-5 ml-4 float-left font-black">
          <span id="minuto">{{ minutos }}</span
          ><span>m</span><span id="segundo">{{ segundos }}</span>
        </div>
        <div class="float-right flex pt-2 pr-2">
          <div class="rounded-full bg-yellow-300 p-1 cursor-pointer">
            <a href="./one">
              <svg
                xmlns="http://www.w3.org/2000/svg"
                fill="none"
                viewBox="0 0 24 24"
                stroke-width="1.5"
                stroke="currentColor"
                class="w-4 h-4"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  d="M10.5 19.5L3 12m0 0l7.5-7.5M3 12h18"
                />
              </svg>
            </a>
          </div>

          <div class="rounded-full bg-blue-300 p-1 ml-2 cursor-pointer" @click="expand()">
            <svg
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
              stroke-width="1.5"
              stroke="currentColor"
              class="w-4 h-4"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="M3.75 3.75v4.5m0-4.5h4.5m-4.5 0L9 9M3.75 20.25v-4.5m0 4.5h4.5m-4.5 0L9 15M20.25 3.75h-4.5m4.5 0v4.5m0-4.5L15 9m5.25 11.25h-4.5m4.5 0v-4.5m0 4.5L15 15"
              />
            </svg>
          </div>
          <a href="/" class="rounded-full bg-red-300 p-1 ml-2">
            <svg
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
              stroke-width="1.5"
              stroke="currentColor"
              class="w-4 h-4"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="M6 18L18 6M6 6l12 12"
              />
            </svg>
          </a>
        </div>
      </div>
      <div
        class="w-full h-full rounded-b-lg flex flex-col items-center justify-center bg-gradient-to-r from-yellow-100 to-yellow"
      >
        <div class="bg-gray-400 rounded-t-full w-16 h-8 shadow-md"></div>
        <div
          class="h-4/6 overflow-hidden flex items-center justify-center py-14 bg-gradient-to-r from-yellow-400 to-red-500 w-3/4 shadow-xl flex-nowrap justify-evenly justify-items-stretch rounded-lg border-double border border-yellow-500"
        >
          <video
            id="myVideo"
            class="h-5/6 rounded-md bg-gray-700 p-1"
            autoplay
          >
            <source
              :src="require(`./../../../static/media/videos/${char}.mp4`)"
              type="video/mp4"
            />
          </video>
          <div
            class="w-1/6 h-full flex flex-col items-center justify-center bg-gray-700 float-right rounded-lg border border-gray-900"
          >
            <div
              v-if="resume"
              @click="pauseVideo(), (resume = false)"
              class="cursor-pointer text-xs font-bold w-14 h-14 bg-red-600 text-white rounded-full flex items-center justify-center hover:bg-red-800 border border-red-800 shadow-md"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                fill="none"
                viewBox="0 0 24 24"
                stroke-width="1.5"
                stroke="currentColor"
                class="w-6 h-6"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  d="M15.75 5.25v13.5m-7.5-13.5v13.5"
                />
              </svg>
            </div>
            <div
              v-if="!resume"
              @click="playVideo(), (resume = true)"
              class="cursor-pointer text-xs font-bold w-14 h-14 bg-blue-700 text-white rounded-full flex items-center justify-center hover:bg-blue-800 border border-blue-800 shadow-md p-4"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                fill="none"
                viewBox="0 0 24 24"
                stroke-width="1.5"
                stroke="currentColor"
                class="w-6 h-6"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  d="M5.25 5.653c0-.856.917-1.398 1.667-.986l11.54 6.348a1.125 1.125 0 010 1.971l-11.54 6.347a1.125 1.125 0 01-1.667-.985V5.653z"
                />
              </svg>
            </div>
            <div
              class="cursor-pointer mt-4 text-xs font-bold w-14 h-14 bg-black text-white rounded-full flex items-center justify-center hover:bg-gray-500"
            >
              SKIP
              <svg
                xmlns="http://www.w3.org/2000/svg"
                fill="none"
                viewBox="0 0 24 24"
                stroke-width="1.5"
                stroke="currentColor"
                class="w-4 h-4 ml-1"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  d="M3 8.688c0-.864.933-1.405 1.683-.977l7.108 4.062a1.125 1.125 0 010 1.953l-7.108 4.062A1.125 1.125 0 013 16.81V8.688zM12.75 8.688c0-.864.933-1.405 1.683-.977l7.108 4.062a1.125 1.125 0 010 1.953l-7.108 4.062a1.125 1.125 0 01-1.683-.977V8.688z"
                />
              </svg>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "Home",
  data() {
    return {
      char: localStorage.getItem("char"),
      segundos: 0,
      minutos: 0,
      resume: true,
      playerName: localStorage.getItem("playerName"),
      expanded: false,
    };
  },
  created() {
    setInterval(this.startTime, 1000);
  },
  methods: {
    expand() {
      this.expanded = !this.expanded;
      if (this.expanded) {
        document.getElementById("container")?.style.setProperty("position", "absolute");
      } else {
        document.getElementById("container")?.style.setProperty("position", "relative");
      }
    },
    playVideo() {
      var vid: any = document.getElementById("myVideo");
      vid.play();
    },
    pauseVideo() {
      var vid: any = document.getElementById("myVideo");
      vid.pause();
    },
    startTime() {
      this.segundos++;
      if (this.segundos == 60) {
        this.minutos++;
        this.segundos = 0;
      }
    },
  },
});
</script>
<style>
@font-face {
  font-family: "JetBrains";
  src: url("./../../../static/fonts/JetBrainsMonoNL-Regular.ttf") format("truetype");
}

.bg-white-op {
  background: #f4f4f4;
}

.body {
  font-family: "JetBrains";
  background: url("./../../../static/media/7.png");
  background-color: #fcf4d2;
}
</style>

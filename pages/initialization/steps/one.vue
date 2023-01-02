<template>
  <div
    class="body shadow-2xl w-3/6 h-4/6 rounded-lg flex items-center justify-center z-0"
  >
    <div
      id="container"
      class="flex w-full h-full flex-col bg-white-op rounded-lg shadow-2xl z-50"
    >
      <div class="w-full h-12">
        <div class="dots-bars-3 mt-4 ml-4 float-left"></div>
        <div class="mt-5 ml-4 float-left font-black">
          <span id="minuto">{{ minutos }}</span
          ><span>m</span><span id="segundo">{{ segundos }}</span>
        </div>
        <div class="float-right flex pt-2 pr-2">
          <div class="rounded-full bg-yellow-300 p-1 cursor-pointer">
            <svg
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
              stroke-width="1.5"
              stroke="currentColor"
              class="w-4 h-4"
            >
              <path stroke-linecap="round" stroke-linejoin="round" d="M19.5 12h-15" />
            </svg>
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
      <div class="w-full h-full rounded-b-lg flex">
        <div class="w-2/6 h-full bg-yellow-50 px-8 rounded-lg">
          <p class="blink_me text-center my-2 font-bold">Choose the features!</p>
          <div class="flex flex-col">
            <h3 class="ml-2 text-xl font-black">Female</h3>
            <span
              @mouseover="chooseOption('1')"
              class="option flex items-center pl-2 w-28 rounded-full bg-yellow-100 cursor-pointer h-8 ml-4 mb-1 shadow-md"
              >Option <b class="text-white bg-blue-600 px-2 ml-2 rounded-full">1</b></span
            >
            <span
              @mouseover="chooseOption('2')"
              class="option flex items-center pl-2 w-28 rounded-full bg-yellow-100 cursor-pointer h-8 ml-6 mb-1 shadow-md"
              >Option <b class="text-white bg-blue-600 px-2 ml-2 rounded-full">2</b></span
            >
            <span
              @mouseover="chooseOption('3')"
              class="option flex items-center pl-2 w-28 rounded-full bg-yellow-100 cursor-pointer h-8 ml-4 mb-1 shadow-md"
              >Option <b class="text-white bg-blue-600 px-2 ml-2 rounded-full">3</b></span
            >
          </div>
          <br />
          <h3 class="ml-4 text-xl font-black">Male</h3>
          <span
            @mouseover="chooseOption('4')"
            class="option flex items-center pl-2 w-28 rounded-full bg-yellow-100 cursor-pointer h-8 ml-4 mb-1 shadow-md"
            >Option <b class="text-white bg-red-500 px-2 ml-2 rounded-full">4</b></span
          >
          <span
            @mouseover="chooseOption('5')"
            class="option flex items-center pl-2 w-28 rounded-full bg-yellow-100 cursor-pointer h-8 ml-6 mb-1 shadow-md"
            >Option <b class="text-white bg-red-500 px-2 ml-2 rounded-full">5</b></span
          >
          <span
            @mouseover="chooseOption('6')"
            class="option flex items-center pl-2 w-28 rounded-full bg-yellow-100 cursor-pointer h-8 ml-4 mb-1 shadow-md"
            >Option <b class="text-white bg-red-500 px-2 ml-2 rounded-full">6</b></span
          >
          <br />
          <h3 class="ml-2 mt-3 text-xl font-black">???</h3>
          <span
            @mouseover="chooseOption('7')"
            class="option flex items-center pl-2 w-28 rounded-full bg-yellow-100 cursor-pointer h-8 ml-4 mb-1 shadow-md"
            >Option
            <b
              class="text-white bg-gradient-to-r from-indigo-500 via-purple-500 to-pink-500 px-2 ml-2 rounded-full"
              >7</b
            ></span
          >
          <span
            @mouseover="chooseOption('8')"
            class="option flex items-center pl-2 w-28 rounded-full bg-yellow-100 cursor-pointer h-8 ml-8 mb-1 shadow-md"
            >Option
            <b
              class="text-white bg-gradient-to-r from-indigo-500 via-purple-500 to-pink-500 px-2 ml-2 rounded-full"
              >8</b
            ></span
          >
          <span
            @mouseover="chooseOption('9')"
            class="option flex items-center pl-2 w-28 rounded-full bg-yellow-100 cursor-pointer h-8 ml-4 mb-1 shadow-md"
            >Option
            <b
              class="text-white bg-gradient-to-r from-indigo-500 via-purple-500 to-pink-500 px-2 ml-2 rounded-full"
              >9</b
            ></span
          >
          <span
          @mouseover="chooseOption('10')"
          class="option flex items-center pl-2 w-28 rounded-full bg-yellow-100 cursor-pointer h-8 ml-8 mb-1 shadow-md"
          >Option
          <b
            class="text-white bg-gradient-to-r from-indigo-500 via-purple-500 to-pink-500 px-2 ml-2 rounded-full"
            >10</b
          ></span
        >   <span
        @mouseover="chooseOption('11')"
        
        class="option flex items-center pl-2 w-28 rounded-full bg-yellow-100 cursor-pointer h-8 ml-4 mb-1 shadow-md"
        >Option
        <b
          class="text-white bg-gradient-to-r from-indigo-500 via-purple-500 to-pink-500 px-2 ml-2 rounded-full"
          >11</b
        ></span
      >
        </div>
        <div class="w-4/6 h-full justify-center flex items-center">
          <div class="w-3/6 h-5/6">
            <h3 class="text-center">{{ playerName }}</h3>
            <Transition name="slide-fade" mode="out-in">
              <img
                class="pt-14 px-14"
                data-placement="bottom"
                :key="charSelected"
                :src="require(`./../../../static/media/chars/${charSelected}`)"
              />
            </Transition>
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
      charSelected: "1.png",
      segundos: 0,
      minutos: 0,
      playerName: localStorage.getItem("playerName"),
      expanded: false,
    };
  },
  created() {
    setInterval(this.startTime, 1000);
  },
  methods: {
    start() {
      this.$router.push("initialization/steps/one");
    },
    expand() {
      this.expanded = !this.expanded;
      if (this.expanded) {
        document.getElementById("container")?.style.setProperty("position", "absolute");
      } else {
        document.getElementById("container")?.style.setProperty("position", "relative");
      }
    },
    startTime() {
      this.segundos++;
      if (this.segundos == 60) {
        this.minutos++;
        this.segundos = 0;
      }
    },
    chooseOption(option: string) {
      // var audio = new Audio(require('./../../../static/media/audio/test.mp3'));
      // audio.autoplay = true;
      // audio.play();
      this.charSelected = option + ".png";
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

.bg-brown {
  background: #624434;
}

.bg-brown-dark {
  background: #36251d;
}

.dots-bars-3 {
  width: 40px;
  height: 26px;
  color: #930404;
  float: left;
  --c: linear-gradient(currentColor 0 0);
  background: var(--c) 0 100%, var(--c) 50% 100%, var(--c) 100% 100%;
  background-size: 8px calc(100% - 4px);
  background-repeat: no-repeat;
  position: relative;
}

.dots-bars-3:before {
  content: "";
  position: absolute;
  width: 8px;
  height: 8px;
  border-radius: 50%;
  background: currentColor;
  left: 0;
  top: 0;
  animation: db3-1 1.5s linear infinite alternate,
    db3-2 0.75s cubic-bezier(0, 200, 0.8, 200) infinite;
}

.option:hover {
  transition: all 0.2s ease-in-out;
  background: #674e40c6;
  transform: translate(15%);
}

.slide-fade-enter-active {
  transition: all 0.4s ease-in-out;
}

.slide-fade-leave-active {
  transition: all 0.3s ease-in-out;
}

.slide-fade-enter-from {
  transform: translate(50%);
  opacity: 0.5;
}
.slide-fade-leave-to {
  transform: translate(-60%);
  opacity: 0;
}

@keyframes blinker {
  50% {
    opacity: 0;
  }
}

@keyframes db3-1 {
  100% {
    left: calc(100% - 8px);
  }
}

@keyframes db3-2 {
  100% {
    top: -0.1px;
  }
}
</style>

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
          ><span>:</span><span id="segundo">{{ segundos }}</span>
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
    </div>
  </div>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "Home",
  data() {
    return {
      segundos: 0,
      minutos: 0,
      playerName: "",
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

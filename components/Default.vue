<template>
  <div class="w-full h-screen body">
    <div class="w-full h-full flex">
      <div class="w-1/3 h-full part-1 flex items-center justify-center">
        <div class="bg-animate w-full h-3/6"></div>
      </div>
      <div class="w-2/3 h-full flex justify-center items-center">
        <div class="w-5/6 h-5/6 font-black text-5xl text-center flex justify-center items-center flex-col">
          <div class="w-3/6">
            <div class="dots-bars-3 float-left"></div>
          </div>
          <div class="text-7xl font-bolder h-1/5 mb-5 px-2 text-center py-2">
            Game of Chooses
            <p class="font-normal mt-2 text-base pt-2 w-3/6 text-center mx-auto mt-2 mb-10">
              Lorem ipsum dolor sit amet consectetur adipisicing elit. Iure blanditiis molestiae neque mstiae neque
              magni culpaagni culpa
            </p>
          </div>
          <a id="banner" href="initialization" class="banner mt-6 pt-3 rounded-full">
            <p class="blink_me mb-4">
              START GAME
            </p>
          </a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "DefaultVue",
  data() {
    return {
      open: true
    }
  },
  created() {
    setTimeout(function () { document.getElementById('banner')?.style.setProperty('width', '50%') }, 400);
  },
  methods: {
    startGame() {
      this.$router.push('home');
    }
  }
};
</script>
<style>
@font-face {
  font-family: "JetBrains";
  src: url('./../static/fonts/JetBrainsMonoNL-Regular.ttf') format("truetype");
}

@keyframes blinker {
  50% {
    opacity: 0;
  }
}

.body {
  font-family: 'JetBrains';
}

.part-1 {
  background-color: #fcf4d2;
}

.bg-animate {
  background: url("./../static/media/2.gif") no-repeat;
  background-size: contain;
}

.blink_me {
  animation: blinker 1.2s linear infinite;
}

.banner {
  cursor: pointer;
  overflow: hidden;
  height: 7.2vh;
  background-color: #794f38b2;
  width: 0;
  transition: 1s;
}

.banner:hover {
  color: white;
  background-color: #624434;
}

.dots-bars-3 {
  width: 40px;
  height: 26px;
  color: #930404;
  float: left;
  --c: linear-gradient(currentColor 0 0);
  background:
    var(--c) 0 100%,
    var(--c) 50% 100%,
    var(--c) 100% 100%;
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
  animation:
    db3-1 1.5s linear infinite alternate,
    db3-2 0.75s cubic-bezier(0, 200, .8, 200) infinite;
}

@keyframes db3-1 {
  100% {
    left: calc(100% - 8px)
  }
}

@keyframes db3-2 {
  100% {
    top: -0.1px
  }
}
</style>

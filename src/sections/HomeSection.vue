<script setup>
import CustomIcons from '@/components/CustomIcons.vue'
import SocialIcons from '@/components/SocialIcons.vue'
</script>

<template>
  <div class="flex justify-around flex-wrap">
    <div class="basis-1/2">
      <div class="container w-fit h-fit mx-auto relative">
        <div class="inner-container w-full h-full relative">
          <div class="img-container overflow-hidden">
            <img class="img" src="/me.png" />
          </div>
        </div>
      </div>
      <div class="flex mx-auto w-fit mt-14 space-x-7">
        <SocialIcons iconName="facebook" customStyle="spin" />
        <SocialIcons iconName="linkedin" customStyle="spin" />
        <SocialIcons iconName="github" customStyle="spin" />
      </div>
    </div>
    <div class="basis-1/2 space-y-7 mt-24">
      <div class="name text-6xl font-bold tracking-widest">DAN ERWIN MAGNO</div>
      <div class="space-y-7">
        <div class="font-bold space-y-2">
          <div class="text-4xl">FRONT END WEB DEVELOPER</div>
          <div class="text-xl">Your partner in developing seamless and interactive websites.</div>
        </div>
        <div class="flex gap-3 flex-wrap mb-3">
          <div class="border border-black p-2 text-xs font-bold rounded-lg flex items-center gap-1">
            <CustomIcons name="web" />
            Web Developer
          </div>
          <div class="border border-black p-2 text-xs font-bold rounded-lg flex items-center gap-1">
            <CustomIcons name="frontend" />
            Front End
          </div>
          <div class="border border-black p-2 text-xs font-bold rounded-lg flex items-center gap-1">
            <CustomIcons name="location" />

            Philippines
          </div>
        </div>
      </div>
      <div class="btn text-lg font-bold w-fit">
        <div class="flex items-center justify-center w-fit btn-container relative">
          <button class="border border-black p-5">DOWNLOAD CV</button>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.img-container {
  height: 420px;
  width: 340px;
}

.img {
  height: 470px;
  width: 340px;
}

@property --angle {
  syntax: '<angle>';
  initial-value: 0deg;
  inherits: false;
}

.container::before,
.container::after {
  --angle: 0deg;
  content: '';
  width: calc(100% + 30px);
  height: calc(70% + 30px);
  background-image: conic-gradient(from var(--angle), transparent 10%, black);
  position: absolute;
  z-index: -2;
  top: 65%;
  left: 50%;
  transform: translate(-50%, -50%);
  animation: spin 10s linear infinite;
  transition:
    width 0.2s,
    height 0.2s ease-in-out;
}

.container::before {
  filter: blur(1.5rem);
  opacity: 0.5;
}

.inner-container::before {
  content: '';
  width: calc(100% + 10px);
  height: calc(70% + 10px);
  background-color: white;
  border: 2px solid white;
  position: absolute;
  z-index: -1;
  top: 65%;
  left: 50%;
  transform: translate(-50%, -50%);
}

@keyframes spin {
  from {
    --angle: 0deg;
  }
  to {
    --angle: 360deg;
  }
}

.btn-container::after {
  content: '';
  position: absolute;
  width: 0%;
  height: 0%;
  background-color: black;
  z-index: -1;
  transition:
    width 0.2s ease-in-out,
    height 0.2s ease-in-out;
}

.btn {
  transition: 0.3s ease-in-out;
}

.btn:hover {
  color: white;
  .btn-container::after {
    width: 100%;
    height: 100%;
  }
}
</style>

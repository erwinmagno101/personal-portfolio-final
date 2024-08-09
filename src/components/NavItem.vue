<script setup>
const props = defineProps({
  title: {
    type: String,
    required: true
  }
})
</script>

<template>
  <div class="relative font-bold cursor-pointer item px-5 py-1">
    <div class="w-full inset-x-0 -top-5 bg-gray-600 absolute top-line"></div>
    <div class="w-full inset-x-0 -bottom-5 bg-gray-600 absolute bottom-line"></div>
    <div class="absolute inset-0 flex items-center justify-center">
      <div class="bg-black bg-block"></div>
    </div>
    <div class="relative z-10 select-none">
      {{ props.title }}
    </div>
  </div>
</template>

<style scoped>
.top-line,
.bottom-line,
.bg-block {
  pointer-events: none;
}

.top-line,
.bottom-line {
  height: 1px;
  opacity: 0;
  transition:
    top 0.3s,
    bottom 0.3s,
    opacity 0.3s;
}

.item {
  color: black;
  transition: 0.3s ease-in-out;
}

.bg-block {
  width: 0px;
  height: 0px;
  transition:
    width 0.2s ease-in-out,
    height 0.2s ease-in-out,
    padding 0.2s ease-in-out;
}

.item:hover {
  color: white;

  .bg-block {
    width: 100%;
    height: 100%;
  }

  .top-line {
    top: -3px;
    opacity: 1;
  }

  .bottom-line {
    bottom: -3px;
    opacity: 1;
  }
}
</style>

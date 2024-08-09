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
    <div class="first absolute inset-0 flex items-center justify-center">
      <div class="bg-black bg-block"></div>
    </div>
    <div class="relative z-10 select-none">
      {{ props.title }}
    </div>
  </div>
</template>

<style scoped>
.first::before,
.first::after {
  content: '';
  width: 100%;
  background-color: gray;
  position: absolute;
  pointer-events: none;
  height: 1px;
  opacity: 0;
  transition:
    top 0.3s,
    bottom 0.3s,
    opacity 0.3s;
}

.first::before {
  left: 0;
  right: 0;
  top: -20px;
}

.first::after {
  left: 0;
  right: 0;
  bottom: -20px;
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
  pointer-events: none;
}

.item:hover {
  color: white;

  .bg-block {
    width: 100%;
    height: 100%;
  }

  .first::before {
    top: -3px;
    opacity: 1;
  }

  .first::after {
    bottom: -3px;
    opacity: 1;
  }
}
</style>

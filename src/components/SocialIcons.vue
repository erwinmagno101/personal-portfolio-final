<script setup>
import CustomIcons from './CustomIcons.vue'

const props = defineProps({
  iconName: { type: String, required: true },
  customStyle: { type: String }
})
</script>
<template>
  <div class="border border-black rounded-full h-fit w-fit parent icon-container overflow-clip">
    <div class="relative icon w-full h-full p-2">
      <CustomIcons :name="props.iconName" :customStyle="props.customStyle" />
    </div>
  </div>
</template>

<style scoped>
.icon::after {
  content: '';
  position: absolute;
  transform-origin: center;
  width: 100%;
  height: 0%;
  bottom: 0;
  right: 0;
  background-color: black;
  z-index: -1;
  transition: height 0.3s ease-in-out;
}

.icon {
  transition: color 0.3s ease-in-out;
}

.icon-container {
  transition: scale 0.2s linear;
}

.icon-container:hover {
  scale: 1.2;

  .icon::after {
    height: 100%;
  }

  .icon {
    color: white;
  }
}
</style>

<script setup>
import NavItem from './NavItem.vue'
</script>

<template>
  <div class="w-full h-16 mt-5 flex items-center justify-between px-16 mb-24">
    <div>LOGO</div>
    <div class="flex space-x-7">
      <NavItem title="HOME" />
      <NavItem title="PORTFOLIO" />
      <NavItem title="CONTACT" />
    </div>
    <div>Options</div>
  </div>
</template>

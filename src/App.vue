<script setup lang="ts">
import dropdown from "./components/dropdown.vue";
</script>

<template>
  <div class="yl flex justify-center items-center w-screen h-screen">
    <div class="">
      <!-- <div class="m-2 w-4 h-4 bg-green-400"></div> -->
      <dropdown />
    </div>
    <div class="absolute top-0 left-0">
      <dropdown />
    </div>
    <div class="absolute top-0 right-0">
      <dropdown />
    </div>
    <div class="absolute bottom-0 left-0">
      <dropdown />
    </div>
    <div class="absolute bottom-0 right-0">
      <dropdown />
    </div>
  </div>
</template>

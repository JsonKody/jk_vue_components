<script setup lang="ts">

</script>

<template>
  <div ref="dropdown" class="dropdown relative">
    <button ref="button" class="rd link button relative">button</button>
    <div ref="dropdown-menu" class="rd dropdown-menu text-black absolute">
      <div class="mt-2 px-4 py-2 bg-white rounded shadow-md">dropdown menu</div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.dropdown-menu {
  top: 100%;
  opacity: 0;
  visibility: hidden;
  transform: translateY(-8px);
  transition: opacity 150ms ease-in-out, visibility 50ms ease-in-out,
    transform 150ms ease-in-out;
}

.link:focus + .dropdown-menu,
.dropdown-menu:hover {
  opacity: 1;
  visibility: visible;
  transform: translateY(0);
}
</style>

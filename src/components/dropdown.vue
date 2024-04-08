<script setup lang="ts">
import { ref, onMounted } from "vue";

const dropdown = ref(null);
const button = ref(null);
const dropdownMenu = ref(null);



// Funkce pro aktualizaci pozice
const updatePopoverPosition = async () => {
  const placement = (binding.arg || "top") as Placement;

  if (el._popover) {
    await computePosition(el, el._popover, {
      // Přidáme middleware
      placement,
      middleware: [offset(8), flip(), shift({ padding: 8 })],
    }).then(({ x, y, placement }) => {
      if (el._popover) {
        // new placement
        el._popover.style.transformOrigin = origins[placement];
      }

      Object.assign(el._popover!.style, {
        top: `${y}px`,
        left: `${x}px`,
      });
    });
  }
};
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

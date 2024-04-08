<script setup lang="ts">
import { ref } from "vue";
import { useFloating, offset, flip, shift } from "@floating-ui/vue";

const dropdown_button = ref(null);
const dropdown_menu = ref(null);

const placement = ref("right");
const middleware = ref([offset(10), flip(), shift()]);

const { update } = useFloating(dropdown_button, dropdown_menu, {
  placement,
  middleware,
});
</script>

<template>
  <div ref="dropdown" class="dropdown relative">
    <button ref="dropdown_button" class="rd link button relative">
      button
    </button>
    <div
      @click="update"
      ref="dropdown_menu"
      class="rd dropdown-menu text-black absolute"
    >
      <div class="mt-2 px-4 py-2 bg-white rounded shadow-md">dropdown menu</div>
    </div>
  </div>
</template>

<style lang="scss" scoped></style>

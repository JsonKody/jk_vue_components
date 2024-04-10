<script setup lang="ts">
import type { Placement } from "@floating-ui/vue";
import { ref, onMounted } from "vue";
import { useFloating, offset, flip, shift } from "@floating-ui/vue";

const dropdown_button = ref(null);
const dropdown_content = ref(null);

const placement = ref<Placement>("bottom-end");
const middleware = ref([offset(10), flip(), shift({ padding: 5 })]);

const { floatingStyles, update,  } = useFloating(
  dropdown_button,
  dropdown_content,
  {
    placement,
    middleware,
  }
);

const is_open = ref(false);

function toggle_button() {
  is_open.value = !is_open.value;
  if (is_open.value) {
    update();
  }
}

onMounted(() => {
  update();
});
</script>

<template>
  <button
    @click="toggle_button"
    ref="dropdown_button"
    class="rd link button relative"
  >
    <slot name="button"></slot>
  </button>
  <div
    :style="floatingStyles"
    data-dropdown_content
    ref="dropdown_content"
    class="flex flex-wrap items-center justify-center text-black bg-white rounded-md overflow-auto"
    :class="{ active: is_open }"
  >
    <slot name="content"></slot>
  </div>
</template>

<style lang="scss" scoped>
[data-dropdown_content] {
  opacity: 0.3;
  transition: opacity 100ms ease-in-out;
  white-space: nowrap;
}
[data-dropdown_content].active {
  opacity: 1;
}
</style>

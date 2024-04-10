<script setup lang="ts">
import type { Placement } from "@floating-ui/vue";
import { ref, onMounted } from "vue";
import { useFloating, offset, flip, shift } from "@floating-ui/vue";

interface Props {
  placement?: Placement;
}

const props = withDefaults(defineProps<Props>(), {
  placement: "bottom",
});

const placement_to_origin: Record<Placement, string> = {
  top: "center bottom",
  "top-start": "left bottom",
  "top-end": "right bottom",
  bottom: "center top",
  "bottom-start": "left top",
  "bottom-end": "right top",
  left: "right center",
  "left-start": "right top",
  "left-end": "right bottom",
  right: "left center",
  "right-start": "left top",
  "right-end": "left bottom",
};

const dropdown_button = ref(null);
const dropdown_content = ref(null);

const placement = ref<Placement>(props.placement);
const middleware = ref([offset(10), flip(), shift({ padding: 5 })]);

const { floatingStyles, update } = useFloating(
  dropdown_button,
  dropdown_content,
  {
    placement,
    middleware,
  }
);

const is_open = ref(false);
const content_clicked = ref(false);

function toggle_button() {
  is_open.value = !is_open.value;
  if (is_open.value) {
    update();
    document.addEventListener("click", handle_click_outside, true);
  } else {
    content_clicked.value = false;
    document.removeEventListener("click", handle_click_outside, true);
  }
}

function content_leave() {
  if (content_clicked.value) {
    content_clicked.value = false;
    is_open.value = false;
    document.removeEventListener("click", handle_click_outside, true);
  }
}

function handle_click_outside(event: MouseEvent) {
  if (
    dropdown_content.value &&
    dropdown_button.value &&
    !(dropdown_content.value as HTMLElement).contains(event.target as Node) &&
    !(dropdown_button.value as HTMLElement).contains(event.target as Node)
  ) {
    is_open.value = false;
    document.removeEventListener("click", handle_click_outside, true);
  }
}

onMounted(() => {
  update();
});
</script>

<template>
  <button @click="toggle_button" ref="dropdown_button" class="relative">
    <slot name="button"></slot>
  </button>
  <div
    @mouseleave="content_leave"
    @click="content_clicked = true"
    :style="{
      ...floatingStyles,
      transformOrigin: placement_to_origin[props.placement],
    }"
    data-dropdown_content
    ref="dropdown_content"
    class="flex flex-wrap items-center justify-center text-black bg-white border rounded-md overflow-auto shadow-md z-30"
    :class="{ active: is_open }"
  >
    <slot name="content"></slot>
  </div>
</template>

<style lang="scss" scoped>
[data-dropdown_content] {
  opacity: 0;
  max-height: 0;
  max-width: calc(100vw - 10px);
  transition: opacity 100ms ease-in-out;
  pointer-events: none;
  border: none;

  &.active {
    opacity: 1;
    max-height: fit-content;
    pointer-events: auto;
  }
}
</style>

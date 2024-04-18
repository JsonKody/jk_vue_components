<script setup lang="ts">
import { ref, watch, onMounted } from "vue";

interface Props {
  modelValue?: boolean;
  position?: "top" | "bottom" | "right" | "left" | "fullscreen";
  showButton?: boolean;
  scroll?: boolean;
  blur?: boolean;
}

const props = withDefaults(defineProps<Props>(), {
  modelValue: undefined,
  position: "fullscreen",
  showButton: true,
  scroll: true,
  blur: false,
});

const emit = defineEmits<{
  (event: "update:modelValue", value: boolean): void;
}>();

const isOpen = ref(props.modelValue ?? false);

function toggleMobileMenu() {
  isOpen.value = !isOpen.value;
}
</script>

<template>
  <button @click="toggleMobileMenu" v-if="props.showButton" class="relative">
    <slot name="button"></slot>
  </button>

  <teleport to="body">
    <transition>
      <div></div>
    </transition>
  </teleport>
</template>

<style lang="scss">
/*
  Dulezite!!
  Important!!
  This code make sure that when there is a least one modal, the body wont scroll
  but when last modal dissapears body would be scroll again.
  (modal must have attribute "data-modal")
*/

body:has([data-modal]) {
  overflow: hidden;
  margin-right: var(--scrollbar-width);
}

/**
Vue transition
 */
.v-enter-active,
.v-leave-active {
  transition: opacity 150ms ease-in-out;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}
</style>

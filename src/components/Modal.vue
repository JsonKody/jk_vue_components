<script setup lang="ts">
import { ref, watch, onMounted } from "vue";

interface Props {
  modelValue?: boolean;
  position?: "top" | "bottom" | "center" | "fullscreen";
  showButton?: boolean;
  scroll?: boolean
  blur?: boolean
}

const props = withDefaults(defineProps<Props>(), {
  modelValue: undefined,
  position: "center",
  showButton: true,
  scroll: true,
  blur: false
});

const emit = defineEmits<{
  (event: "update:modelValue", value: boolean): void;
}>();

const isOpen = ref(props.modelValue ?? false);

watch(
  () => props.modelValue,
  (newVal) => {
    if (newVal !== undefined) {
      isOpen.value = newVal;
    }
  }
);

watch(isOpen, (newVal) => {
  if (props.modelValue !== undefined) {
    emit("update:modelValue", newVal);
  }

  if(isOpen.value) {
    setScrollbarWidthVar()
  }
});

function toggleModal() {
  isOpen.value = !isOpen.value;
}


function computeScrollbarWidth() {
  const bodyStyle = window.getComputedStyle(document.body);
  const marginRight = parseInt(bodyStyle.marginRight);

  if (marginRight > 0) {
    console.log('je margin')
    return marginRight;
  } else {
    console.log('je scrollbar')
    return window.innerWidth - document.documentElement.clientWidth;
  }
}

function setScrollbarWidthVar() {
  const width = computeScrollbarWidth()
  document.documentElement.style.setProperty('--scrollbar-width', width + 'px');
}



onMounted(() => {
  if (props.modelValue !== undefined) {
    isOpen.value = props.modelValue;
  }
});
</script>

<template>
  <button @click="toggleModal" v-if="props.showButton" class="relative">
    <slot name="button"></slot>
  </button>

  <teleport to="body">
    <transition>
    <div
      data-modal
      v-if="isOpen"
      @click="toggleModal"
      class="fixed inset-0 flex justify-center bg-black bg-opacity-50"
      :class="{
        'items-center': position == 'center',
        'items-end': position == 'bottom',
        'items-start': position == 'top',
        'backdrop-blur-sm': props.blur
      }"
    >
      <div
        @click.stop
        class="bg-white text-black"
        :class="{
          'md:m-2 md:rounded-md absolute inset-0 max-h-dvh':
            position == 'fullscreen',
          'm-2 rounded-md max-h-[calc(100dvh-1rem)]': position != 'fullscreen',
          'overflow-auto': props.scroll,
          'overflow-hidden': !props.scroll
        }"
      >
          <slot name="content"></slot>
    
      </div>
      <div
        class="absolute flex items-center justify-center md:m-3 m-1 top-0 right-0 w-8 h-8 bg-black rounded-full bg-opacity-20 transition duration-150 hover:bg-opacity-50 cursor-pointer"
      >
        <svg
          xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 24 24"
          stroke-width="2"
          stroke="currentColor"
          fill="none"
          stroke-linecap="round"
          stroke-linejoin="round"
        >
          <path stroke="none" d="M0 0h24v24H0z" fill="none" />
          <path d="M18 6l-12 12" />
          <path d="M6 6l12 12" />
        </svg>
      </div>
    </div>
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
   transition: opacity 150ms ease-in-out
}

.v-enter-from,
.v-leave-to {
   opacity: 0;
}
</style>

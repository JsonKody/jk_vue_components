<script setup lang="ts">
import { ref, watch, onMounted } from "vue";

interface Props {
  modelValue?: boolean; // Použití modelValue místo open pro v-model, volitelné
  position?: "top" | "bottom" | "center" | "fullscreen"; // Pozice modálu
  showButton?: boolean; // Příznak, zda zobrazit tlačítko pro ovládání modálu
}

// Definování výchozích hodnot pro props
const props = withDefaults(defineProps<Props>(), {
  modelValue: undefined, // Výchozí hodnota je undefined, protože použití modelValue je volitelné
  position: "center",
  showButton: true,
});

const emit = defineEmits<{
  (event: "update:modelValue", value: boolean): void;
}>();

// Lokální stav pro otevření/zavření modálu, inicializovaný na základě modelValue, pokud je k dispozici
const isOpen = ref(props.modelValue ?? false);

// Sleduje změny modelValue pro aktualizaci isOpen, pouze pokud je modelValue definováno
watch(
  () => props.modelValue,
  (newVal) => {
    if (newVal !== undefined) {
      isOpen.value = newVal;
    }
  }
);

// Emituje změnu při otevření/zavření modálu, pouze pokud je modelValue definováno
watch(isOpen, (newVal) => {
  if (props.modelValue !== undefined) {
    emit("update:modelValue", newVal);
  }

  if (newVal) {
    disableScrolling();
  } else {
    enableScrolling();
  }
});

// Funkce pro přepnutí viditelnosti modálu
function toggleModal() {
  isOpen.value = !isOpen.value;
}

function disableScrolling() {
  document.body.style.position = "fixed";
  document.body.style.top = `-${window.scrollY}px`;
}

function enableScrolling() {
  // When the modal is hidden, we want to remain at the top of the scroll position
  document.body.style.position = "";
  document.body.style.top = "";
}

// Inicializace modálu při montáži
onMounted(() => {
  if (props.modelValue !== undefined) {
    isOpen.value = props.modelValue;
  }
});
</script>

<template>
  <button @click="toggleModal" v-if="props.showButton" class="relative">
    {{ isOpen }}
    <slot name="button"></slot>
  </button>

  <teleport to="body">
    <div
      v-if="isOpen"
      @click="toggleModal"
      class="fixed inset-0 flex justify-center bg-black bg-opacity-50 backdrop-blur-sm"
      :class="{
        'items-center': position == 'center',
        'items-end': position == 'bottom',
        'items-start': position == 'top',
      }"
    >
      <div
        @click.stop
        class="bg-white text-black overflow-hidden"
        :class="{
          'md:m-2 md:rounded-md absolute inset-0 max-h-dvh':
            position == 'fullscreen',
          'm-2 rounded-md max-h-[calc(100dvh-1rem)]': position != 'fullscreen',
        }"
      >
        <div class="the-modal max-h-full overflow-auto">
          <slot name="content"></slot>
        </div>
      </div>
      <div
        class="absolute md:m-3 m-1 p-1 top-0 right-0 w-9 h-9 bg-black rounded-full bg-opacity-20 transition duration-150 hover:bg-opacity-50 cursor-pointer"
      >
        <svg
          xmlns="http://www.w3.org/2000/svg"
          class="icon icon-tabler icon-tabler-x"
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
  </teleport>
</template>

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
});

// Funkce pro přepnutí viditelnosti modálu
function toggleModal() {
  isOpen.value = !isOpen.value;
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
    <slot name="button">Otevřít</slot>
  </button>

  <teleport to="body">
    <div
      v-if="isOpen"
      @click="toggleModal"
      class="fixed inset-0 flex justify-center bg-black bg-opacity-50"
      :class="{
        'items-center': position == 'center',
        'items-end': position == 'bottom',
        'items-start': position == 'top',
      }"
    >
      <div
        @click.stop
        class="m-2 modal_content bg-white rounded-md text-black overflow-hidden"
      >
        <slot name="content"></slot>
      </div>
    </div>
  </teleport>
</template>

<style lant="scss" scoped>
.modal_content {
  max-height: calc(100vh - 1.5rem);
  max-width: calc(100vw - 1.5rem);

  &/deep/ img {
    max-height: 100%;
    object-fit: contain;
  }
}
</style>

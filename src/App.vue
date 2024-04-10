<script setup lang="ts">
import Dropdown from "./components/Dropdown.vue";
import Modal from "./components/Modal.vue";
import { ref } from "vue";

const isModalOpen = ref(false);
</script>

<template>
  <div class="yl flex justify-center items-center w-screen h-screen">
    <div class="flex flex-col gap-4">
      <button @click="isModalOpen = true">modal bez tlacitka - TOP</button>

      <!-- modal bez tlacitka -->
      <Modal v-model="isModalOpen" position="top" :showButton="false">
        <template #content>modal bez tlacitka</template>
      </Modal>

      <!-- modal s tlacitkem -->
      <Modal position="bottom">
        <template #button>modal s tlacitkem - BOTTOM</template>
        <template #content>modal s tlacitkem</template>
      </Modal>

      <!-- modal s big image -->
      <Modal position="center">
        <template #button>BGIMG_button</template>
        <template #content>
          <img src="/big_image.webp" alt="velmi siroky obr" />
        </template>
      </Modal>

      <!-- modal s big image V -->
      <Modal position="center">
        <template #button>BGIMG_V__button</template>
        <template #content>
          <img src="/big_image_v.webp" alt="velmi vysoky obr" />
        </template>
      </Modal>

      <Dropdown>
        <template #button>button</template>
        <template #content>
          <div class="flex">
            <ul class="border">
              <li class="border-2 border-yellow-400">
                123 123 12o3i joij123 123 12o3i joij123 123 12o3i joij123 123
                12o3i joij123 123 12o3i joij123 123 12o3i joij123 123 12o3i
                joij123 123 12o3i joij123 123 12o3i joij123 123 12o3i joij123
              </li>
              <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
              <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
              <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
              <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
              <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
              <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
              <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
              <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
              <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
              <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
              <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
            </ul>
          </div></template
        >
      </Dropdown>
    </div>
    <div class="rd w-screen absolute top-0 left-0">
      <Dropdown>
        <template #button>button</template>
        <template #content>
          <div class="flex">
            <ul class="border">
              <li class="border-2 border-yellow-400">
                123 123 12o3i joij123 123 12o3i joij123 123 12o3i joij123 123
                12o3i joij123 123 12o3i joij123 123 12o3i joij123 123 12o3i
                joij123 123 12o3i joij
              </li>
              <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
              <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
              <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
              <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
              <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
              <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
              <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
            </ul>
          </div>
        </template>
      </Dropdown>
    </div>
    <div class="absolute top-0 right-0">
      <Dropdown>
        <template #button>button</template>
        <template #content
          ><div class="flex">
            <ul class="border">
              <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
              <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
              <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
              <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
              <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
              <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
              <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
              <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
            </ul>
          </div>
        </template>
      </Dropdown>
    </div>
    <div class="absolute bottom-0 left-0">
      <Dropdown>
        <template #button>button</template>
        <template #content
          ><div class="flex">
            <ul class="border">
              <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
              <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
              <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
              <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
              <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
              <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
              <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
              <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
            </ul>
          </div>
        </template>
      </Dropdown>
    </div>
    <div class="absolute bottom-0 right-0">
      <Dropdown>
        <template #button>button</template>
        <template #content
          ><div class="flex">
            <ul class="border">
              <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
              <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
              <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
              <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
              <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
              <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
              <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
              <li class="border-2 border-yellow-400">123 123 12o3i joij</li>
            </ul>
          </div>
        </template>
      </Dropdown>
    </div>
  </div>
</template>

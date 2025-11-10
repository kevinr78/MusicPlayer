<template>
  <div>
    <div class="scrollable-wrapper controls">
      <h2>{{ title }}</h2>
      <button class="nav-arrows showOnDesktop left" @click="scrollLeft">
        <ChevronLeft />
      </button>
      <div class="scrollable" ref="scrollContainer">
        <slot></slot>
      </div>
      <button class="nav-arrows showOnDesktop right" @click="scrollRight">
        <ChevronRight />
      </button>
    </div>
  </div>
</template>
<script setup lang="ts">
import { ChevronRight, ChevronLeft } from "lucide-vue-next";

import { ref } from "vue";

const props = defineProps({
  title: {
    type: String,
    required: true,
  },
});

const scrollContainer = ref<HTMLDivElement | null>(null);

const scrollLeft = () => {
  if (scrollContainer.value) {
    scrollContainer.value.scrollBy({ left: -300, behavior: "smooth" });
  }
};

const scrollRight = () => {
  if (scrollContainer.value) {
    scrollContainer.value.scrollBy({ left: 300, behavior: "smooth" });
  }
};
</script>
<style scoped>
.scrollable-wrapper {
  position: relative;
  width: 100%;
  height: 100%;
}

.scrollable {
  display: flex;
  justify-content: space-around;
  gap: 1rem;
  overflow-x: auto;
  scroll-behavior: smooth;
  padding: 1rem;
  scrollbar-width: none;
}

.scrollable::-webkit-scrollbar {
  display: none; /* hide scrollbar in Chrome/Safari */
}

.nav-arrows {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  background: rgba(0, 0, 0, 0.5);
  border: none;
  color: white;
  border-radius: 50%;
  width: 40px;
  height: 40px;
  cursor: pointer;
  z-index: 10;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: background 0.3s;
  transform: tr;
}

.nav-arrow:hover {
  background: rgba(0, 0, 0);
}

.left {
  left: -1rem;
}

.right {
  right: 1rem;
}
.showOnDesktop {
  display: none;
}

@media (min-width: 768px) {
  .showOnDesktop {
    display: flex;
    opacity: 0;
  }

  .scrollable-wrapper:hover .showOnDesktop {
    opacity: 1;
  }

  .scrollable-wrapper:hover .left {
    transform: translateX(2rem) translateY(-50%);
    transition: all 0.6s;
  }

  .scrollable-wrapper:hover .right {
    transform: translateX(-2rem) translateY(-50%);
    transition: all 0.3s;
  }
}
</style>

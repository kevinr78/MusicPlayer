<script setup lang="ts">
import { ref } from "vue";

defineProps<{ msg: string }>();

const count = ref(0);
</script>

<template>
  <p>
    Lorem ipsum dolor, sit amet consectetur adipisicing elit. Reiciendis, cum.
  </p>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>

<template>
  <div class="card">
    <div>
      <div class="card_image_conatiner">
        <figure>
          <img
            class="card_image"
            src="../assets/acid_trip.png"
            alt="Album Cover"
          />
        </figure>
      </div>
      <div class="card_details">
        <h5>Teenge Lobotomy</h5>
        <p class="text-truncate">The Ramones</p>
      </div>
    </div>
    <div class="card_actions">
      <button v-if="isPlaying" class="play_button btn">
        <Play />
      </button>
      <button v-if="!isPlaying" class="pause_button btn">
        <Pause />
      </button>
    </div>
  </div>
</template>
<script setup lang="ts">
import { Play, Pause } from "lucide-vue-next";

const isPlaying = true;
</script>
<style scoped>
.card {
  position: relative;
}

.card_image_conatiner {
  margin-bottom: 1rem;
}
.card_actions {
  opacity: 0;
  position: absolute;
  right: 1rem;
  bottom: 1rem;
  transition: transform 0.3s ease-in-out, opacity 0.3s ease-in-out;
  overflow: hidden;
}
.card:hover .card_actions {
  opacity: 1;
  transform: translateY(-120%);
  overflow: hidden;
}

.card_image {
  width: 10rem;
  max-height: 8rem;
  min-height: 6rem;
}

.text-truncate {
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;
}

.card_actions button {
  background-color: var(--color-primary-dark);
  border-radius: 15rem;
  color: var(--color-text-primary);
}
</style>

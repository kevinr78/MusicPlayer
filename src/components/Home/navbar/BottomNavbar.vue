<template>
  <nav class="bottom_navbar">
    <div class="bottom_navbar_container">
      <div class="bottom_navbar_link">
        <router-link to="/" class="router-link">
          <House />
          <!-- <span class="text-sm">House</span> -->
        </router-link>
      </div>
      <div class="bottom_navbar_link">
        <router-link to="/search" class="">
          <Search />
          <!--  <span class="text-sm">Search</span> -->
        </router-link>
      </div>
      <div class="bottom_navbar_link">
        <router-link to="/library" class="">
          <GalleryVerticalEnd />
          <!-- <span class="text-sm">Library</span> -->
        </router-link>
      </div>
      <div class="bottom_navbar_link">
        <router-link to="/settings" class="">
          <User />
          <!--  <span class="text-sm font-medium">Settings</span> -->
        </router-link>
      </div>
    </div>
  </nav>
</template>

<script setup lang="ts">
import { House, Search, GalleryVerticalEnd, User } from "lucide-vue-next";
</script>

<style scoped>
.bottom_navbar {
  position: fixed;
  bottom: 0;
  width: 100%;
  background-color: var(--color-bg);
  padding: 10px 0;
  display: flex;
  justify-content: center;
  box-shadow: 0 -2px 5px rgba(0, 0, 0, 0.3);
  height: 60px;
}

.bottom_navbar_container {
  display: flex;
  justify-content: space-around;
  align-items: center;
  width: 100%;
}

.bottom_navbar_link:hover {
  color: var(--color-primary);
  transform: scale(1.1);
  transition: transform 0.2s;
  border-radius: 2px;
  padding: 6px;
}
</style>

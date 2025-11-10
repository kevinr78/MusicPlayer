<template>
  <main>
    <TopNavbar />
    <section class="cards_container">
      <ScrollableContainer title="Recently Played">
        <Card />
        <Card />
        <Card />
        <Card />
        <Card />
        <Card />
        <Card />
        <Card />
      </ScrollableContainer>
      <ScrollableContainer title="Most Played">
        <Card />
        <Card />
        <Card />
        <Card />
        <Card />
        <Card />
        <Card />
        <Card />
      </ScrollableContainer>
      <ScrollableContainer title="Randomly Played">
        <Card />
        <Card />
        <Card />
        <Card />
        <Card />
        <Card />
        <Card />
        <Card />
      </ScrollableContainer>
      <ScrollableContainer title="Randomly Played">
        <Card />
        <Card />
        <Card />
        <Card />
        <Card />
        <Card />
        <Card />
        <Card />
      </ScrollableContainer>
    </section>
    <BottomNavbar />
  </main>
</template>

<script setup lang="ts">
import Card from "@/components/Card.vue";
import TopNavbar from "@/components/Home/navbar/TopNavbar.vue";
import ScrollableContainer from "@/components/shared/ScrollableContainer.vue";
import BottomNavbar from "@/components/Home/navbar/BottomNavbar.vue";
</script>

<style scoped>
main {
  width: 100%;
  height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  background-color: var(--color-background);
  box-sizing: border-box;
}
.cards_container {
  width: 100%;
  margin: 2rem 0;
  padding: 0 1rem;
  height: 250px;
  display: flex;
  flex-direction: column;
}
</style>

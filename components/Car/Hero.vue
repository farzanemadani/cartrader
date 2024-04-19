<template>
  <!-- Home Hero -->
  <div class="w-100 hero-bg relative h-screen bg-cover bg-bottom bg-no-repeat">
    <!-- Your content here -->
    <div class="absolute z-10 flex h-full w-full items-center justify-center">
      <div class="w-1/2 text-center">
        <h1 class="mb-10 font-serif text-8xl text-white">Find your drive</h1>
        <!-- HOME SEARCH BAR -->
        <CarSearchBar />
        <!-- HOME SEARCH BAR -->
      </div>
    </div>
    <div class="z-1 absolute h-full w-full bg-black opacity-50"></div>
  </div>
  <!-- Home Hero -->
</template>
<script setup lang="ts"></script>
<style scoped>
.hero-bg {
  background-image: url(../../public/assets/img/hero-bg.jpeg);
}
</style>

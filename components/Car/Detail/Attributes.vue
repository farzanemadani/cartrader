<template>
  <div class="mr-10 mt-5 border-b pb-5">
    <div
      v-for="(feature, index) in features"
      :key="index"
      class="mt-2 flex text-lg"
    >
      <p class="mr-3 rounded text-lime-800">✔️</p>
      <p>{{ feature }}</p>
    </div>
  </div>
</template>
<script setup>
const props = defineProps({
  features: Array,
});
</script>

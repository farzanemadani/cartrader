<template>
  <div class="w-full">
    <CarCard
      v-for="car in cars"
      :key="car.id"
      :car="car"
      @favor="handleFavarite"
      :favored="car.id in favarite"
    />
  </div>
</template>
<script setup>
  import { useLocalStorage } from "@vueuse/core";
  const { cars } = useCars();

  const favarite = useLocalStorage("favorite", {});

  const handleFavarite = (id) => {
    if (id in favarite.value) {
      delete favarite.value[id];
    } else {
      favarite.value = {
        ...favarite.value,
        [id]: true,
      };
    }
  };
</script>

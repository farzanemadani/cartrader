<template>
  <div>
    <div
      class="relative mb-5 h-[200px] w-full cursor-pointer overflow-hidden border shadow"
    >
      <img
        class="absolute right-4 top-4 z-20 w-7"
        :src="favored ? heartFilled : heartOutline"
        @click="favored = !favored"
      />
      <div
        @click="navigateTo(`/car/${car.name}-${car.id}`)"
        class="flex h-full"
      >
        <NuxtImg class="h-full w-[250px]" :src="car.url" :alt="car.name" />

        <div class="flex flex-col p-4">
          <div>
            <h1 class="text-2xl text-blue-700">{{ car.name }}</h1>
            <p class="text-gray-700">{{ car.description }}</p>
          </div>
          <h1 class="mt-auto text-xl">${{ car.price }}</h1>
        </div>
      </div>
    </div>
  </div>
</template>
<script setup>
import heartFilled from "@/public/assets/img/heartFilled.png";
import heartOutline from "@/public/assets/img/heartOutline.png";

const props = defineProps({
  car: Object,
});

const favored = useState(`favored-${props.car.id}`, () => {
  return false;
});
</script>

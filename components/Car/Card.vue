<template>
    <div>
         <div 
         @click="navigateTo(`/car/${car.name}-${car.id}`)"
         class="shadow border w-full overflow-hidden mb-5 cursor-pointer h-[200px]">
            <div class="flex h-full">
                  <img
                  class="w-[250px] h-full"
                  :src="car.url" 
                  :alt="car.name">

                  <div class="p-4 flex flex-col">
                    <div>
                      <h1 class="text-2xl text-blue-700">{{ car.name }}</h1> 
                      <p class="text-gray-700">{{ car.description }}
                      </p>
                    </div>
                    <h1 class="mt-auto text-xl">${{ car.price }}</h1>
                  </div>
              </div>
          </div>
    </div>
</template>
<script setup>
const props = defineProps({
  car:Object
})
</script>
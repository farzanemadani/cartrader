<template>
  <div
    class="mx-auto flex w-[600px] justify-between overflow-hidden rounded-full bg-white font-serif text-2xl drop-shadow-2xl"
  >
    <input
      v-model="city"
      type="text"
      class="w-full rounded-full px-5 py-3 text-2xl focus:outline-none"
      :class="cityError ? 'border border-red-500' : ''"
      placeholder="Search by city ..."
    />
    <button class="bg-sky-500 px-10 text-white" @click="handleSearch">
      Search
    </button>
  </div>
</template>
<script setup lang="ts">
const city = ref("");
const cityError = ref(false);
const router = useRouter();

const handleSearch = () => {
  if (!city.value) {
    return (cityError.value = true);
  }
  navigateTo(`/city/${city.value}/car`);
};
</script>

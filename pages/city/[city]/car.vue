<template>
  <NuxtLayout name="custom">
    <div class="mt-32 flex">
      <NuxtErrorBoundary>
        <CarSideBar />
        <NuxtPage />
        <template #error="{ error }">
          <div class="mx-auto flex flex-col text-center">
            <h1 class="mb-6 text-5xl text-red-400">
              Sorry, something went wrong
            </h1>
            <code>{{ error }}</code>
            <button
              @click="goBack"
              class="mt-4 rounded bg-blue-400 px-10 py-3 text-white"
            >
              Go Back
            </button>
          </div>
        </template>
      </NuxtErrorBoundary>
      <!-- <CarCards/> -->
    </div>
  </NuxtLayout>
</template>
<script setup>
const { capitalizeFirstLetter } = useUtilities();
const route = useRoute();
useHead({
  title: `${route.params.city ? capitalizeFirstLetter(route.params.city) : "Cars"} in ${capitalizeFirstLetter(
    route.params.city,
  )}`,
});

const router = useRouter();
const goBack = () => {
  router.back();
};
</script>

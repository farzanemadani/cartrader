<template>
    <NuxtLayout name="custom">
      <div class="mt-32 flex">
        <NuxtErrorBoundary>
          <CarSideBar/>
          <NuxtPage/>
          <template #error="{error}">
          <div class="text-center mx-auto flex flex-col">
            <h1 class="text-5xl text-red-400 mb-6">Sorry, something went wrong</h1>
            <code>{{ error }}</code>
            <button @click="error.value == null" class="text-white bg-blue-400 px-10 py-3 rounded mt-4">Go Back</button>
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
    title: `${ route.params.city ? capitalizeFirstLetter(route.params.city) : 'Cars' } in ${capitalizeFirstLetter(route.params.city)}`
})


</script>
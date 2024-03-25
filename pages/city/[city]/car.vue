<template>
    <NuxtLayout name="custom">
      <div class="mt-32 flex">
        <CarSideBar/>
        <NuxtPage/>
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
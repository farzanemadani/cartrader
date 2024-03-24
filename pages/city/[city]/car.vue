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

const route = useRoute();
useHead({
    title: `${ route.params.city ? capitalizeFirstLetter(route.params.city) : 'Cars' } in ${capitalizeFirstLetter(route.params.city)}`
})

function capitalizeFirstLetter(string) {
  return string.charAt(0).toUpperCase() + string.slice(1);
}

</script>
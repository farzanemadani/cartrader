<template>
    <div class="mx-auto mt-4 max-w-7xl space-y-4 px-4 xs:px-8 sm:px-10 lg:px-0 pb-16 w-4/5">
      <div class="mt-32 flex">
        <CarSideBar/>
        <NuxtPage/>
        <!-- <CarCards/> -->
      </div>
    </div>
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
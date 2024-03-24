<template>
<div>
    <Navbar></Navbar>
    <div class="mx-auto mt-4 max-w-7xl space-y-4 px-4 xs:px-8 sm:px-10 lg:px-0 pb-16 w-4/5">
      <CarDetailHero />
      <CarDetailAttributes />
      <CarDetailDescription />
      <CarDetailContact />
    </div>
</div>
</template>
<script setup>
 const route = useRoute();
 useHead({
  title: capitalizeFirstLetter(route.params.name),
 })

function capitalizeFirstLetter(string) {
  return string.charAt(0).toUpperCase() + string.slice(1);
}
</script>
<template>
  <div>
    <NuxtLayout name="custom">
        <CarDetailHero />
        <CarDetailAttributes />
        <CarDetailDescription />
        <CarDetailContact />
    </NuxtLayout>
  </div>
</template>
<script setup>
const route = useRoute();
useHead({
  title: capitalizeFirstLetter(route.params.name),
});


function capitalizeFirstLetter(string) {
  return string.charAt(0).toUpperCase() + string.slice(1);
}
</script>
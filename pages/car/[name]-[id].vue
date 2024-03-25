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
const { capitalizeFirstLetter } = useUtilities();
useHead({
  title: capitalizeFirstLetter(route.params.name),
});

</script>
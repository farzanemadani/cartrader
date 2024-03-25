<template>
  <div>
    <NuxtLayout name="custom">
        <CarDetailHero :car="car" />
        <CarDetailAttributes :features="car.features"/>
        <CarDetailDescription :description="car.description"/>
        <CarDetailContact />
    </NuxtLayout>
  </div>
</template>
<script setup>
const route = useRoute();
const { cars } = useCars();
const { capitalizeFirstLetter } = useUtilities();
useHead({
  title: capitalizeFirstLetter(route.params.name),
});
const car = computed(()=>{
  return cars.find((item)=> {
    return item.id === parseInt(route.params.id)
  })
})

if(!car.value){
  throw createError({
    statusCode:404,
    message:`Car with id of  ${ route.params.id } does not exit`
  })
}
</script>
<template>
  <!-- CAR SIDE BAR -->
  <div class="z-30 mr-10 h-[190px] w-64 border shadow">
    <div class="relative flex cursor-pointer justify-between border-b p-5">
      <h3>Locations</h3>
      <h3 @click="updateModal('location')" class="capitalize text-blue-400">
        {{ route.params.city }}
      </h3>
      <div
        v-if="modal.location"
        class="absolute left-56 top-1 -m-1 border bg-white p-5 shadow"
      >
        <input v-model="city" type="text" class="rounded border p-1" />
        <button
          @click="onChangeLocation"
          class="mt-2 w-full rounded bg-blue-400 p-1 text-white"
        >
          Apply
        </button>
      </div>
    </div>

    <div class="relative flex cursor-pointer justify-between border-b p-5">
      <h3>Make</h3>
      <h3 @click="updateModal('make')" class="capitalize text-blue-400">
        Toyota
      </h3>
      <div
        v-if="modal.make"
        class="absolute left-56 top-1 -m-1 border bg-white p-5 shadow"
      >
        <input type="text" class="rounded border p-1" />
        <button class="mt-2 w-full rounded bg-blue-400 p-1 text-white">
          Apply
        </button>
      </div>
    </div>

    <div class="relative flex cursor-pointer justify-between border-b p-5">
      <h3>Price</h3>
      <h3 @click="updateModal('price')" class="capitalize text-blue-400">
        Any
      </h3>
      <div
        v-if="modal.price"
        class="absolute left-56 top-1 -m-1 border bg-white p-5 shadow"
      >
        <input type="text" class="rounded border p-1" />
        <button class="mt-2 w-full rounded bg-blue-400 p-1 text-white">
          Apply
        </button>
      </div>
    </div>
  </div>
  <!-- CAR SIDE BAR -->
</template>
<script setup>
const modal = ref({
  make: false,
  location: false,
  price: false,
});

const city = ref("");
const route = useRoute();

const updateModal = (key) => {
  modal.value[key] = !modal.value[key];
  if (!isNaN(parseInt(city.value))) {
    throw createError({
      statusCode: 400,
      message: "invalid city format",
    });
  }
};

const onChangeLocation = () => {
  if (!city.value) return;
  if (!isNaN(parseInt(city))) {
    throw createError({
      statusCode: 400,
      message: "Invalid city format",
    });
  }
  updateModal("location");
  navigateTo(`/city/${city.value}/car/${route.params.make}`);
  city.value = "";
};
</script>

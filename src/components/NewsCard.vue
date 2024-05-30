<script setup>
defineProps({
  title: String,
  date: String,
  desc: String,
});
</script>
<template>
  <div class="col">
    <div class="card h-100 rounded-4 shadow-sm p-2 my-3 effect">
      <div class="card-body">
        <h3 class="fw-bold fs-5 mb-2 pb-1">{{ title }}</h3>
        <h6 class="card-subtitle mb-2 text-body-secondary">{{ date }}</h6>
        <div class="mb-3">
          {{ desc }}
        </div>
      </div>
    </div>
  </div>
</template>
<style scoped>
.effect {
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}
.effect:hover {
  transform: translateY(-2px);
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}
</style>

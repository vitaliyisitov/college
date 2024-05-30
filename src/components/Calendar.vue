<script setup>
const tooltipTriggerList = document.querySelectorAll(
  '[data-bs-toggle="tooltip"]'
);
const tooltipList = [...tooltipTriggerList].map(
  (tooltipTriggerEl) => new bootstrap.Tooltip(tooltipTriggerEl)
);
</script>
<template>
  <div class="container my-5">
    <div class="row">
      <div class="col-12 col-lg-2"></div>
      <div class="col-12 col-lg-8">
        <div class="ratio ratio-4x3">
          <iframe
            class="rounded-4 shadow-sm"
            src="https://calendar.yandex.ru/embed/month?&layer_ids=29039791&tz_id=Europe/Moscow&layer_names=сайт"
            width="800"
            height="450"
            frameborder="0"
            style="border: 1px solid #eee"
          ></iframe>
        </div>
      </div>
      <div class="col-12 col-lg-2"></div>
    </div>
  </div>
</template>

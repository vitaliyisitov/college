<script setup>
import { ref, onMounted, watch, defineProps, inject } from "vue";

const schedules = ref([]);

const fetchAnalysis = async () => {
  try {
    const response = await fetch("https://2e56d847a3bcdb41.mokky.dev/schedule");
    const data = await response.json();
    schedules.value = data;
  } catch (error) {
    console.error("Ошибка при выполнении запроса:", error);
  }
};

onMounted(fetchAnalysis);
</script>
<template>
  <div class="col-12" v-for="schedule in schedules" :key="schedule.id">
    <div class="card rounded-4 shadow-sm my-4">
      <div class="card-header rounded-top-4 bg-white py-2 fw-medium fs-5">
        <div class="row">
          <div class="col-11">
            {{ schedule.name }}
            <h6 class="card-subtitle my-1 text-body-secondary">
              {{ schedule.number }} урок | {{ schedule.time }} | каб. №
              {{ schedule.cabinet }}
            </h6>
          </div>
          <div class="col-1 d-flex justify-content-center align-items-center">
            <span
              :class="[
                'badge mx-1 rounded',
                schedule.grade === '5'
                  ? 'text-bg-success'
                  : schedule.grade === '4'
                  ? 'text-bg-primary'
                  : schedule.grade === '3'
                  ? 'text-bg-warning'
                  : 'text-bg-danger',
              ]"
              >{{ schedule.grade }}</span
            >
          </div>
        </div>
      </div>
      <div class="card-body">
        <p class="fs-6 fw-normal">
          <i class="bi bi-house-door-fill"></i> Домашнее задание:
          {{ schedule.homework }}
        </p>
      </div>
    </div>
  </div>
</template>
<style scoped></style>

<script setup>
import ScheduleCard from "./ScheduleCard.vue";
</script>
<template>
  <div class="container my-5">
    <!-- <h3 class="fw-semibold fs-3 my-4 pb-1 text-center">Дневник</h3> -->
    <div class="row">
      <div class="col-12 col-lg-1"></div>
      <div class="col-12 col-lg-10">
        <ul
          class="nav nav-pills d-flex justify-content-evenly text-danger"
          role="tablist"
        >
          <li class="nav-item">
            <a class="nav-link active" data-bs-toggle="pill" href="#monday"
              >20 | Понедельник</a
            >
          </li>
          <li class="nav-item">
            <a class="nav-link" data-bs-toggle="pill" href="#tuesday"
              >21 | Вторник</a
            >
          </li>
          <li class="nav-item">
            <a class="nav-link" data-bs-toggle="pill" href="#wednesday"
              >22 | Среда</a
            >
          </li>
          <li class="nav-item">
            <a class="nav-link" data-bs-toggle="pill" href="#thursday"
              >23 | Четверг</a
            >
          </li>
          <li class="nav-item">
            <a class="nav-link" data-bs-toggle="pill" href="#friday"
              >24 | Пятница</a
            >
          </li>
          <li class="nav-item">
            <a class="nav-link" data-bs-toggle="pill" href="#saturday"
              >25 | Суббота</a
            >
          </li>
          <li class="nav-item">
            <a class="nav-link" data-bs-toggle="pill" href="#sunday"
              >26 | Воскресенье</a
            >
          </li>
        </ul>
        <div class="tab-content">
          <div id="monday" class="container tab-pane active">
            <ScheduleCard></ScheduleCard>
          </div>
          <div id="tuesday" class="container tab-pane fade">
            <ScheduleCard></ScheduleCard>
          </div>
          <div id="wednesday" class="container tab-pane fade">
            <ScheduleCard></ScheduleCard>
          </div>
          <div id="thursday" class="container tab-pane fade">
            <ScheduleCard></ScheduleCard>
          </div>
          <div id="friday" class="container tab-pane fade">
            <ScheduleCard></ScheduleCard>
          </div>
          <div id="saturday" class="container tab-pane fade">
            <ScheduleCard></ScheduleCard>
          </div>
          <div id="sunday" class="container tab-pane fade">
            <ScheduleCard></ScheduleCard>
          </div>
        </div>
      </div>
      <div class="col-12 col-lg-1"></div>
    </div>
  </div>
</template>

<style scoped>
.nav-link:not(.active) {
  background-color: #c1c1c1;
  color: #000;
}

.nav-link.active {
  background-color: #0d6efd;
  color: #fff;
}

.nav-link {
  border-radius: 10px;
  padding: 0.5rem 1rem;
  margin: 5px;
}
</style>

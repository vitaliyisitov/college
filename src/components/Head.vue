<script setup>
import { ref, reactive, provide, defineProps, inject, computed } from "vue";
import News from "./News.vue";
import Schedule from "./Schedule.vue";
import Calendar from "./Calendar.vue";
import Profile from "./Profile.vue";
const routes = {
  "/": News,
  "/schedule": Schedule,
  "/calendar": Calendar,
  "/profile": Profile,
};

const currentPath = ref(window.location.hash);

window.addEventListener("hashchange", () => {
  currentPath.value = window.location.hash;
});

const currentView = computed(() => {
  return routes[currentPath.value.slice(1) || "/"] || NotFound;
});

function exit() {
  window.location.reload();
}

const aboutUser = inject("aboutUser");
</script>

<template>
  <header class="p-3 mb-5 border-bottom text-bg-dark sticky-top">
    <div class="container">
      <div
        class="d-flex flex-wrap align-items-center justify-content-center justify-content-lg-start"
      >
        <a
          href="#/"
          class="d-flex align-items-center mb-2 mb-lg-0 link-body-emphasis text-decoration-none"
        >
          <img
            src="/media/nk.png"
            alt="Logo"
            width="57"
            height="42"
            class="d-inline-block align-text-top"
          />
        </a>

        <ul
          class="nav col-12 col-lg-auto me-lg-auto mb-2 justify-content-center mb-md-0"
        >
          <li><a href="#/" class="nav-link px-2 text-white">Главная</a></li>
          <li>
            <a href="#/schedule" class="nav-link px-2 text-white">Расписание</a>
          </li>
          <li>
            <a href="#/calendar" class="nav-link px-2 text-white">Календарь</a>
          </li>
        </ul>

        <div class="dropdown text-end">
          <a
            href=""
            class="d-block link-body-emphasis text-decoration-none dropdown-toggle text-secondary"
            data-bs-toggle="dropdown"
            aria-expanded="false"
          >
            <img
              :src="aboutUser[0].avatar"
              alt="mdo"
              width="32"
              height="32"
              class="rounded-circle"
              style="object-fit: cover"
            />
          </a>
          <ul class="dropdown-menu text-small">
            <li><a class="dropdown-item" href="#/profile">Профиль</a></li>
            <!-- <li><a class="dropdown-item" href="#">Настройки</a></li> -->
            <li><hr class="dropdown-divider" /></li>
            <li>
              <a class="dropdown-item" href="#" @click="exit">Выйти</a>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </header>
  <component :is="currentView" />
</template>

<style scoped>
a {
  text-decoration: none;
}
</style>

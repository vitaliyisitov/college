<script setup>
import { ref, reactive, provide, defineProps, inject } from "vue";

const aboutUser = inject("aboutUser");
</script>
<template>
  <div class="container my-5">
    <div class="row g-4">
      <div class="col-12 col-lg-12"></div>
      <div class="col-12 col-lg-12"></div>
      <div class="col-12 col-lg-4">
        <div class="card h-100 rounded-3 shadow">
          <div class="card-header rounded-top-3 bg-white py-3">
            <img
              :src="aboutUser[0].avatar"
              :alt="'avatar of ' + aboutUser[0].name"
              style="width: 150px; height: 150px; object-fit: cover"
              class="img-fluid mx-auto d-block my-3 rounded-pill"
            />
            <h5 class="card-title fw-bold fs-4 mb-2 pb-1 text-center">
              {{ aboutUser[0].name }}
            </h5>
            <h6 class="card-subtitle mb-2 text-body-secondary text-center">
              Подтверждённая учётная запись
              <i class="bi bi-patch-check-fill text-primary"></i>
            </h6>
          </div>
          <div
            class="card-body d-flex align-items-center justify-content-center"
          >
            <div class="alert alert-primary" role="alert">
              Для обновления данных, отправьте
              <a href="https://vk.com/nkcolledge" class="alert-link">запрос</a>.
              <br /><i class="bi bi-stopwatch"></i>
              Мы ответим в течение 24 часов.
            </div>
          </div>
        </div>
      </div>
      <div class="col-12 col-lg-8">
        <div class="row g-4">
          <div class="col-12 col-lg-12">
            <div class="card h-100 rounded-3 shadow">
              <div
                class="card-header rounded-top-3 bg-white py-3 fw-medium fs-5"
              >
                Личные данные
              </div>
              <div class="card-body">
                <p class="fs-6">
                  <strong>Имя и фамилия: </strong
                  >{{ aboutUser[0].name + " " + aboutUser[0].surname }}
                </p>
                <p class="fs-6">
                  <strong>Дата рождения: </strong>{{ aboutUser[0].bday }}
                </p>
                <p class="fs-6">
                  <strong>Группа:</strong> {{ aboutUser[0].group }}
                </p>
              </div>
            </div>
          </div>
          <div class="col-12 col-lg-12">
            <div class="card h-100 rounded-3 shadow">
              <div
                class="card-header rounded-top-3 bg-white py-3 fw-medium fs-5"
              >
                Показатели учебной деятельности
              </div>
              <div class="card-body">
                <p class="fs-6">
                  <strong
                    >Средний балл по результатам последней сессии:
                  </strong>
                  {{ aboutUser[0].average }}
                </p>
                <p class="fs-6">
                  <strong>Средний балл обучения </strong
                  >{{ aboutUser[0].average }}
                </p>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="col-12 col-lg-12"></div>
      <div class="col-12 col-lg-12"></div>
      <div class="col-12 col-lg-12"></div>
      <div class="col-12 col-lg-12"></div>
      <div class="col-12 col-lg-12"></div>
      <div class="col-12 col-lg-12"></div>
    </div>
  </div>
</template>

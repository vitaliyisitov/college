<script setup>
import NewsCard from "./NewsCard.vue";
</script>
<template>
  <div class="container my-5">
    <!-- <div class="row">
      <div class="col-12 col-lg-4"></div>
      <div class="col-12 col-lg-4 text-bg-dark rounded-pill my-3">
        <h3 class="fw-semibold fs-3 my-4 pb-1 text-center">
          <i class="bi bi-newspaper"></i> Новости
        </h3>
      </div>
      <div class="col-12 col-lg-4"></div>
    </div> -->
    <div class="row">
      <div class="col-12 col-lg-2"></div>
      <div class="col-12 col-lg-8">
        <NewsCard
          title="Новое направление"
          date="12.06.2024"
          desc="На сайте появилась возможность записаться на подготовку по Программированию"
        ></NewsCard>
        <NewsCard
          title="Контрольные работы"
          date="10.06.2024"
          desc="Чтобы не забыть про контрольные работы, можно отслеживать данные в календаре"
        ></NewsCard>
        <NewsCard
          title="Личный кабинет"
          date="28.05.2024"
          desc="Теперь, вы можете узнавать расписание прямо здесь"
        ></NewsCard>
      </div>
      <div class="col-12 col-lg-2"></div>
    </div>
  </div>
</template>
<style scoped></style>

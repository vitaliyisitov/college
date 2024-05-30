<script setup>
import { ref, reactive, provide, defineProps, inject } from "vue";
import Head from "./components/Head.vue";
import News from "./components/News.vue";
import Calendar from "./components/Calendar.vue";
import Footer from "./components/Footer.vue";

const aboutUser = ref([]);
const isAuthenticated = ref();

const userCheck = reactive({
  login: "",
  password: "",
});

const onChangeLogin = (event) => {
  userCheck.login = event.target.value;
};

const onChangePassword = (event) => {
  userCheck.password = event.target.value;
};

const showPass = ref(false);

const fetchUsers = async () => {
  try {
    const response = await fetch(
      `https://2e56d847a3bcdb41.mokky.dev/users?login=${userCheck.login}&password=${userCheck.password}`
    );
    const data = await response.json();

    if (data && Object.keys(data).length !== 0) {
      aboutUser.value = data;
      isAuthenticated.value = true;
    } else {
      isAuthenticated.value = false;
      setTimeout(() => {
        isAuthenticated.value = undefined;
      }, 3000);
    }
  } catch (error) {
    console.error("Ошибка при выполнении запроса:", error);
  }
};

provide("aboutUser", aboutUser);
</script>

<template>
  <template v-if="!isAuthenticated">
    <div class="container my-5 rounded-4 py-5 px-4 shadow bg-white">
      <div class="p-5 text-center">
        <img
          class="d-block mx-auto mb-4"
          src="../public/media/nk2.jpeg"
          alt=""
          width="140"
          height="100"
        />
        <h1 class="text-body-emphasis">Личный кабинет</h1>
        <p class="col-lg-8 mx-auto fs-5 text-muted">
          для студентов Налогового колледжа
        </p>
      </div>
      <div
        v-if="isAuthenticated == false"
        class="alert alert-danger mb-4"
        role="alert"
      >
        <strong>Логин или пароль неверный.</strong> Попробуйте ввести данные
        заново!
      </div>
      <form>
        <div class="mb-3">
          <label for="login" class="form-label">Логин</label>
          <input
            type="text"
            class="form-control"
            id="login"
            v-model.trim="login"
            @input="onChangeLogin"
          />
        </div>
        <div class="mb-3">
          <label for="password" class="form-label">Пароль</label>
          <input
            :type="showPass ? 'text' : 'password'"
            class="form-control"
            id="password"
            v-model.trim="password"
            @input="onChangePassword"
          />
        </div>
        <div class="mb-3 form-check">
          <input
            type="checkbox"
            class="form-check-input"
            id="showpassword"
            v-model="showPass"
          />
          <label class="form-check-label" for="showpassword"
            >Показать пароль</label
          >
        </div>
        <div class="d-grid gap-2 d-md-block mt-5">
          <button @click="fetchUsers" class="btn btn-primary" type="button">
            Войти
          </button>
        </div>
      </form>
    </div>
  </template>
  <template v-else> <Head></Head> <Footer></Footer></template>
</template>

<style scoped></style>

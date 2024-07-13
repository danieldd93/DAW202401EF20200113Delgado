<template>
  <q-page class="login-page">
    <div class="login-card q-pa-md">
      <q-card-section class="text-center q-py-xl">
        <div style="position: absolute; top: 10px; left: 10px; z-index: 1000">
          <img src="" style="height: 100px; width: auto" />
        </div>
        <q-avatar size="80px" class="q-mb-md">
          <q-icon name="person" size="56ppx" color="brown" />
        </q-avatar>
        <div
          style="font-size: 1.5em; color: black; font-weight: 100"
          class="text-center"
        >
          Login
        </div>
      </q-card-section>
      <q-card-section>
        <q-form @submit="onSubmit">
          <q-input
            outlined
            v-model="user.email"
            label="Username"
            dense
            class="q-mb-md"
            prepend-inner-icon="account_circle"
            color="red"
            required
          />
          <q-input
            outlined
            v-model="user.password"
            label="Password"
            type="password"
            dense
            class="q-mb-md"
            prepend-inner-icon="lock"
            color="brown"
            required
          />
          <q-btn
            type="button"
            @click="signIn"
            icon="login"
            color="brown"
            label="Entrar"
            class="full-width q-mb-md"
            unelevated
            style="background: linear-gradient(to right, #ffc061, #d38c2f)"
          />
        </q-form>
      </q-card-section>
    </div>
  </q-page>
</template>

<script>
export default {
  name: "LoginForm",
  data() {
    return {
      user: {
        email: "",
        password: "",
      },
    };
  },
  methods: {
    signIn() {
      let URL = "/user/signin";
      this.$api
        .post(URL, this.user)
        .then((response) => {
          localStorage.setItem("userData", JSON.stringify(response.data));
          this.$router.push("/products");
        })
        .catch((error) => {
          console.log(JSON.stringify(error));
        });
    },
  },
};
</script>

<style scoped>
.login-page {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  background: linear-gradient(135deg, #e69e18 0%, #925a06 100%);
}

.login-card {
  background: rgba(255, 255, 255, 1);
  border-radius: 15px;
  padding: 2rem;
  max-width: 400px;
  width: 100%;
  box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1);
  backdrop-filter: blur(10px);
  -webkit-backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.3);
}

.q-input__inner {
  color: #000;
}

.q-input__inner:focus,
.q-input__inner:active,
.q-input__inner {
  border-color: rgba(0, 0, 0, 0.3);
}
</style>

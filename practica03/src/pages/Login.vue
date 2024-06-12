<template>
  <q-page class="login-page">
    <div class="login-card q-pa-xs">
      <q-card-section class="text-center q-py-xs">
        <q-avatar size="80px" class="q-mb-md">
          <q-icon name="person" size="56px" color="primary" />
        </q-avatar>
      </q-card-section>
      <q-card-section class="text-center q-py-xl">
        <div class="text-h4 q-mb-md">Login</div>
        <q-form @submit="onSubmit">
          <q-input
            outlined
            v-model="username"
            label="Username"
            dense
            class="q-mb-md"
            prepend-inner-icon="account_circle"
            required
          />
          <q-input
            outlined
            v-model="password"
            label="Password"
            type="password"
            dense
            class="q-mb-md"
            prepend-inner-icon="lock"
            required
          />
          <div class="text-center q-mb-md">
            <q-btn flat label="Te olvidaste tu contraseña?" color="primary" @click="onForgotPassword" />
          </div>
          <q-btn
            type="submit"
            label="ENTRAR"
            color="primary"
            class="full-width q-mb-md"
            unelevated
            style="background: linear-gradient(to right, #56CCF2, #2F80ED);"
          />
        </q-form>
        <div class="row justify-center q-mt-md">
          <q-btn fab mini round color="blue-8" class="q-mx-xs">
            <q-icon name="facebook" />
          </q-btn>
        </div>
        <div class="q-mt-md">O registrate por el formulario</div>
        <q-btn flat label="REGISTRARSE" color="primary" class="q-mt-md" @click="onSignUp" />
      </q-card-section>
    </div>
  </q-page>
</template>

<script>
export default {
  name: 'LoginPage',
  data () {
    return {
      username: '',
      password: ''
    }
  },
  methods: {
    onSubmit () {
      // Handle login logic here
      alert(`Username: ${this.username}, Password: ${this.password}`);
    },
    onForgotPassword() {
      // Handle forgot password logic
      alert('Forgot Password clicked');
    },
    onSignUp() {
      // Handle sign up logic
      alert('Sign Up clicked');
    }
  }
}
</script>

<style scoped>
.login-page {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
}

.login-card {
  background: #fff;
  border-radius: 15px;
  padding: 2rem;
  max-width: 400px;
  width: 100%;
  box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1);
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

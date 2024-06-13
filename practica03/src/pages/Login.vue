<template>
  <q-page class="login-page">
    <div class="login-card q-pa-md">
      <q-card-section class="text-center q-py-xl">
        <q-avatar size="80px" class="q-mb-md">
          <q-icon name="person" size="56px" color="red" />
        </q-avatar>
      </q-card-section>

      <q-card-section>
        <q-form @submit="onSubmit">
          <q-input
            outlined
            v-model="username"
            label="Username"
            dense
            class="q-mb-md"
            prepend-inner-icon="account_circle"
            color="red"
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
            color="red"
            required
          />
          <div class="text-right q-mb-md">
            <q-btn flat label="Forgot password?" color="red" @click="onForgotPassword" />
          </div>
          <q-btn
            type="submit"
            icon="login"
            color="red"
            class="full-width q-mb-md"
            unelevated
            style="background: linear-gradient(to right, #FF6F61, #D32F2F);"
          />
        </q-form>
        <div class="q-mt-md text-center">Or Sign Up Using</div>
        <div class="row justify-center q-mt-md">
          <q-btn fab mini round color="blue-8" class="q-mx-xs">
            <q-icon name="facebook" />
          </q-btn>
          <q-btn fab mini round color="blue" class="q-mx-xs">
            <q-icon name="twitter" />
          </q-btn>
          <q-btn fab mini round color="red-5" class="q-mx-xs">
            <q-icon name="google" />
          </q-btn>
        </div>
        <div class="q-mt-md text-center">Or Sign Up Using</div>
        <q-btn flat label="SIGN UP" color="red" class="q-mt-md" @click="onSignUp" />
      </q-card-section>
    </div>
  </q-page>
</template>

<script>
export default {
  name: 'LoginPage',
  data() {
    return {
      username: '',
      password: ''
    }
  },
  methods: {
    onSubmit() {
      // Aquí puedes manejar la lógica del login
      // Por ejemplo, puedes agregar una llamada a una API para autenticar al usuario
      // Si el login es exitoso, redirige a la página de productos
      this.$router.push('/products');
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
  background: linear-gradient(135deg, #FF6F61 0%, #D32F2F 100%);
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

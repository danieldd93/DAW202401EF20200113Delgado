<template>
  <q-layout view="hHh lpR fFf">
    <q-header class="bg-brown-8 text-white">
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="toggleLeftDrawer"
          class="text-white"
        />
        <q-toolbar-title> MovieDB </q-toolbar-title>
        <img
          src=""
          alt="Logo"
          style="height: 30px; margin-left: auto; margin-right: 10px"
        />
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      bordered
      class="text-black"
    >
      <q-list>
        <q-item-label header>Menu</q-item-label>

        <q-item to="/products" class="text-brown">
          <q-item-section avatar>
            <q-icon name="store" />
          </q-item-section>
          <q-item-section>
            <q-item-label>Series</q-item-label>
          </q-item-section>
        </q-item>

        <!-- Botón de Salir -->
        <q-item clickable @click="logout">
          <q-item-section avatar>
            <q-icon name="exit_to_app" />
          </q-item-section>
          <q-item-section>
            <q-item-label>Salir</q-item-label>
          </q-item-section>
        </q-item>

        <!-- Añadir más elementos de menú según sea necesario -->
      </q-list>
    </q-drawer>

    <q-page-container class="bg-brown-1 text-dark">
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
export default {
  name: "MainLayout",
  data() {
    return {
      leftDrawerOpen: false,
    };
  },
  methods: {
    toggleLeftDrawer() {
      this.leftDrawerOpen = !this.leftDrawerOpen;
    },
    logout() {
      // Redirigir al usuario a la página de login
      this.$router.push("/login");
    },
  },
};
</script>

<style scoped>
.bg-red-8 {
  background-color: #c62828 !important;
}

.bg-red-2 {
  background-color: #ffcdd2 !important;
}

.bg-red-1 {
  background-color: #ffebee !important;
}
</style>

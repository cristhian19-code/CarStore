<template>
  <vs-navbar dark center-collapsed text-white>
    <template #left>
      <nuxt-link to="/">
        <img
          src="../assets/1580290827car-race-logo-freesvg.org.svg"
          alt=""
          height="70"
      /></nuxt-link>
    </template>
    <vs-navbar-item to="/"> Inicio </vs-navbar-item>

    <vs-navbar-group>
      Categorias
      <template #items>
        <vs-navbar-item
          v-for="category in categories"
          :id="category"
          :key="category"
          :active="category.toLowerCase() == $route.params.category"
          :to="`/categoria/${category.toLowerCase()}`"
        >
          {{ category }}
        </vs-navbar-item>
      </template>
    </vs-navbar-group>

    <vs-navbar-group>
      Nuestras redes

      <template #items>
        <h5 class="title">Redes</h5>

        <vs-navbar-item
          v-for="social in redes"
          :id="social.name"
          :key="social.name"
        >
          <i :class="social.icon"></i> {{ social.name }}
        </vs-navbar-item>
      </template>
    </vs-navbar-group>

    <vs-navbar-item id="License" to="/nosotros">
      Sobre Nosotros
    </vs-navbar-item>

    <vs-navbar-item to="/contactanos"> Contactanos </vs-navbar-item>

    <template #right>
      <vs-button success flat @click="session = !session">Login</vs-button>
    </template>
    <!-- Dialos para el registro e iniciar sesion -->
    <DialogSessionVue />
  </vs-navbar>
</template>

<script>
import { ref, provide, inject } from '@vue/composition-api'
import DialogSessionVue from './DialogSession.vue'
export default {
  components: {
    DialogSessionVue,
  },
  setup() {
    const session = ref(false)
    provide('session', session)

    const category = inject('category')
    return {
      session,
      category,
    }
  },
  data() {
    return {
      categories: [
        'CAMIONETAS',
        'COMERCIALES',
        'DEPORTIVOS',
        'FAMILIARES',
        'HATCHBACK',
        'SEDANES',
        'TODOS',
      ],
      redes: [
        { name: 'Facebook', icon: 'bx bxl-facebook' },
        { name: 'Instagram', icon: 'bx bxl-instagram' },
        { name: 'Whatsapp', icon: 'bx bxl-whatsapp' },
        { name: 'Twitter', icon: 'bx bxl-twitter' },
        { name: 'Messenger', icon: 'bx bxl-messenger' },
      ],
    }
  },
}
</script>

<style scoped>
.vs-navbar-content {
  padding: 5px;
}
</style>
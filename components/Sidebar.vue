<template>
  <div class="sidebar">
    <vs-navbar v-model="active" center-collapsed shadow dark>
      <template #left>
        <vs-button flat success icon @click="activeSidebar = !activeSidebar">
          <i class="bx bx-menu"></i>
        </vs-button>
      </template>
      <template #right>
        <vs-button success flat @click="session = !session">Login</vs-button>
      </template>
    </vs-navbar>
    <vs-sidebar v-model="active" :open.sync="activeSidebar" absolute>
      <template #logo>
        <!-- ...img logo -->
      </template>
      <vs-sidebar-item id="home">
        <template #icon>
          <i class="bx bx-home"></i>
        </template>
        Home
      </vs-sidebar-item>
      <vs-sidebar-group>
        <template #header>
          <vs-sidebar-item arrow>
            <template #icon>
              <i class="bx bx-car"></i>
            </template>
            Categorias
          </vs-sidebar-item>
        </template>

        <vs-sidebar-item
          v-for="category in categories"
          :id="category"
          :key="category"
          :to="`/categoria/${category.toLowerCase()}`"
        >
          {{ category }}
        </vs-sidebar-item>
      </vs-sidebar-group>
      <vs-sidebar-item id="services">
        <template #icon>
          <i class="bx bxs-car-mechanic"></i>
        </template>
        Servicios
      </vs-sidebar-item>
      <vs-sidebar-group>
        <template #header>
          <vs-sidebar-item arrow>
            <template #icon>
              <i class="bx bx-group"></i>
            </template>
            Contactanos
          </vs-sidebar-item>
        </template>

        <vs-sidebar-item id="Instagram">
          <template #icon>
            <i class="bx bxl-instagram"></i>
          </template>
          Instagram
        </vs-sidebar-item>
        <vs-sidebar-item id="twitter">
          <template #icon>
            <i class="bx bxl-twitter"></i>
          </template>
          Twitter
        </vs-sidebar-item>
        <vs-sidebar-item id="Facebook">
          <template #icon>
            <i class="bx bxl-facebook"></i>
          </template>
          Facebook
        </vs-sidebar-item>
      </vs-sidebar-group>

      <vs-sidebar-item id="shopping">
        <template #icon>
          <i class="bx bxs-cart-alt"></i>
        </template>
        Pedido
      </vs-sidebar-item>
      <vs-sidebar-item id="chat">
        <template #icon>
          <i class="bx bx-chat"></i>
        </template>
        Chat
      </vs-sidebar-item>
      <template #footer>
        <vs-row justify="space-between">
          <vs-avatar>
            <img
              src="https://images.pexels.com/photos/220453/pexels-photo-220453.jpeg?auto=compress&cs=tinysrgb&h=650&w=940"
              alt=""
            />
          </vs-avatar>

          <vs-avatar badge-color="danger" badge-position="top-right">
            <i class="bx bx-bell"></i>

            <template #badge> 28 </template>
          </vs-avatar>
        </vs-row>
      </template>
    </vs-sidebar>
    <DialogSessionVue />
  </div>
</template>

<script>
import { ref, provide } from '@vue/composition-api'
import DialogSessionVue from './DialogSession.vue'

export default {
  components: {
    DialogSessionVue,
  },
  setup(props) {
    const session = ref(false)
    provide('session', session)
    return {
      active: 'home',
      session,
      activeSidebar: false,
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
      ],
    }
  },
}
</script>

<style scoped>
.vs-navbar-content {
  padding: 5px 0 5px 0;
}
</style>
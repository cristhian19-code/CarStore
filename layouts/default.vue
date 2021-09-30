<template>
  <main class="default-main">
    <NavbarVue v-if="windowWidth > 900" />
    <SidebarVue v-else />
    <nuxt />
  </main>
</template>

<script>
import { provide, ref } from '@vue/composition-api'
import NavbarVue from '../components/Navbar.vue'
import SidebarVue from '../components/Sidebar.vue'
export default {
  components: {
    NavbarVue,
    SidebarVue,
  },
  setup() {
    const category = ref('')
    provide('category', category)
    return {
      category,
    }
  },
  data() {
    return {
      windowWidth: 1000,
    }
  },
  mounted() {
    window.onresize = () => {
      this.windowWidth = window.innerWidth
    }
  },
}
</script>
<style>
.default-main {
  height: 100vh;
}
</style>
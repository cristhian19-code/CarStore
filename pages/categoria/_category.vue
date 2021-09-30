<template>
  <div class="category">
    <div class="portada">
      <img
        src="https://static.foxdealer.com/635/2020/11/VP_Desktop_3840x1575copy-nuevo-versa.jpg.ximg_.l_full_m.smart_.jpg"
        width="100%"
        alt=""
      />
      <p class="text-category">
        {{
          $route.params.category[0].toUpperCase() +
          $route.params.category.slice(1)
        }}
      </p>
    </div>
    <div class="card-car-catergory">
      <CardCategoryVue
        v-for="item in filter"
        :key="item.name"
        :card="item"
        type="2"
      />
      <DialogDetailsCarVue />
    </div>
    <FooterVue />
  </div>
</template>

<script>
import { provide, ref } from '@vue/composition-api'
import CardCategoryVue from '../../components/CardCar.vue'
import DialogDetailsCarVue from '../../components/DialogDetailsCar.vue'
import FooterVue from '../../components/Footer.vue'

export default {
  components: {
    CardCategoryVue,
    FooterVue,
    DialogDetailsCarVue,
  },
  setup() {
    const activeFullScreen = ref(false)
    const dataDialogCard = ref({})
    provide('activeFullScreen', activeFullScreen)
    provide('dataDialogCard', dataDialogCard)

    return {
      activeFullScreen,
      dataDialogCard
    }
  },
  data() {
    return {
      cars: [
        {
          url: 'https://www.toyotaperu.com.pe/sites/default/files/360/4runner_rojomica3R3_05.jpg',
          cuotas: 5633,
          total: 204660,
          name: 'TOYOTA 4RUNNER',
          category: 'camionetas',
        },
        {
          url: 'https://www.toyotaperu.com.pe/sites/default/files/C-HR-Techo-negro--gris-celestial-metalico-2-_0.png',
          cuotas: 3421,
          total: 124884,
          name: 'TOYOTA C-HR',
          category: 'camionetas',
        },
        {
          url: 'https://www.toyotaperu.com.pe/sites/default/files/360/corollacross_rojomica3R3_05.jpg',
          cuotas: 2767,
          total: 95364,
          name: 'TOYOTA COROLLA CROSS',
          category: 'camionetas',
        },
        {
          url: 'https://www.toyotaperu.com.pe/sites/default/files/360/hiace_beige4R4_05.jpg',
          cuotas: 3204,
          total: 114840,
          name: 'TOYOTA HIACE',
          category: 'comerciales',
        },
        {
          url: 'https://www.toyotaperu.com.pe/sites/default/files/360/hilux-negromica218_05.jpg',
          cuotas: 2691,
          total: 93960,
          name: 'HILUX',
          category: 'comerciales',
        },
        {
          url: 'https://www.toyotaperu.com.pe/sites/default/files/auto-deportivo-blanco-toyota-86.png',
          cuotas: 3755,
          total: 132444,
          name: 'TOYOTA 86',
          category: 'deportivos',
        },
        {
          url: 'https://www.toyotaperu.com.pe/sites/default/files/360/rush_rojomicametalicoR54_05.jpg',
          cuotas: 2233,
          total: 78804,
          name: 'RUSH',
          category: 'familiares',
        },
        {
          url: 'https://www.toyotaperu.com.pe/sites/default/files/360/lcprado_turquesa221_05.jpg',
          cuotas: 5292,
          total: 190296,
          name: 'LAND CRUISER PRADO',
          category: 'familiares',
        },
        {
          url: 'https://www.toyotaperu.com.pe/sites/default/files/360/agya_naranjaR71_05.jpg',
          cuotas: 1187,
          total: 39924,
          name: 'AGYA',
          category: 'hatchback',
        },
        {
          url: 'https://www.toyotaperu.com.pe/sites/default/files/360/priusc_amarillo5A3_05.jpg',
          cuotas: 2441,
          total: 84564,
          name: 'PRIUS C',
          category: 'hatchback',
        },
        {
          url: 'https://www.toyotaperu.com.pe/sites/default/files/360/yaris_azulmetalico218R3_05.jpg',
          cuotas: 1985,
          total: 58752,
          name: 'YARIS SEDAN',
          category: 'sedanes',
        },
      ],
      filter: [],
    }
  },
  created() {
    if (this.$route.params.category === 'todos') {
      this.filter = this.cars
    } else {
      this.filter = this.cars.filter(
        (item) => item.category === this.$route.params.category
      )
    }
  },
}
</script>

<style >
body {
  margin: 0;
  padding: 0;
}

.category {
  display: flex;
  flex-direction: column;
}

.portada {
  position: relative;
  margin-top: 50px;
}

.text-category {
  position: absolute;
  bottom: 0;
  width: 100%;
  text-align: center;
  font-size: 40px;
  color: white;
}

.card-car-catergory {
  padding: 10px;
  display: flex;
  grid-gap: 20px;
  justify-content: center;
  flex-wrap: wrap;
}
</style>
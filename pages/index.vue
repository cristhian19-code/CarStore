<template>
  <div class="home">
    <div class="carousel-cars">
      <splide :style="{ 'margin-top': '60px' }" :options="options">
        <splide-slide
            v-for="(item, index) in img_carousel" :key="index"
        >
          <img
            class="img-slide"
            :src="item"
            alt=""
          />
        </splide-slide>
      </splide>
    </div>
    <div class="categories">
      <p class="title-section">Categorias</p>
      <div class="cards-categories">
        <CardCategoryVue
          v-for="category in categories"
          :key="category.url"
          :card="category"
        />
      </div>
    </div>
    <FooterVue />
  </div>
</template>

<script>
import { provide, ref } from '@vue/composition-api'
import CardCategoryVue from '../components/CardCar.vue'
import FooterVue from '../components/Footer.vue'

export default {
  components: {
    CardCategoryVue,
    FooterVue,
  },
  layout: 'default',
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
      options: {
        type: 'loop',
        rewind: true,
        perPage: 1,
        gap: '1rem',
        autoplay: true,
        pauseOnHover: false,
        arrows: 'slider',
        height: 500,
      },
      img_carousel:[
        "https://www.toyotaperu.com.pe/sites/default/files/360/4runner_azulmica8S6_03.jpg",
        "https://www.toyotaperu.com.pe/sites/default/files/360/4runner_rojomica3R3_03.jpg",
        "https://www.toyotaperu.com.pe/sites/default/files/CorollaHybrid-marron_0.png",
        "https://www.toyotaperu.com.pe/sites/default/files/360/hilux-grisoscurometalico1G3_05.jpg",
        "https://www.toyotaperu.com.pe/sites/default/files/toyota-prius-negro_1_0.png",
        "https://www.toyotaperu.com.pe/sites/default/files/360/corollacross_rojomica3R3_05.jpg",
      ],
      categories: [
        {
          category: 'CAMIONETAS',
          url: 'https://www.toyotaperu.com.pe/sites/default/files/C-HR-Techo-negro--Blanco-perla-2-_0.png',
        },
        {
          category: 'COMERCIALES',
          url: 'https://www.toyotaperu.com.pe/sites/default/files/360/hiace_beige4R4_05.jpg',
        },
        {
          category: 'DEPORTIVOS',
          url: 'https://www.toyotaperu.com.pe/sites/default/files/auto-deportivo-azul-platinado-toyota-86.png',
        },
        {
          category: 'FAMILIARES',
          url: 'https://www.toyotaperu.com.pe/sites/default/files/toyota-fj-cruiser-negro_1_0.png',
        },
        {
          category: 'HATCHBACK',
          url: 'https://www.toyotaperu.com.pe/sites/default/files/360/priusc_amarillo5A3_05.jpg',
        },
        {
          category: 'SEDANES',
          url: 'https://www.toyotaperu.com.pe/sites/default/files/360/etios1636_rojomicametalico3R3_03.jpg',
        },
      ],
    }
  },
}
</script>

<style>
html,
body {
  padding: 0;
  margin: 0;
}

* {
  box-sizing: border-box;
}

.splide__slide {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.home {
  display: flex;
  flex-direction: column;
  width: 100vw;
  height: 100vh;
  overflow-y: scroll;
}

.categories,
.contact {
  display: flex;
  flex-direction: column;
}

.cards-categories {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  grid-gap: 10px;
}

.title-section {
  font-size: 40px;
  font-weight: 400;
  font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande',
    'Lucida Sans', Arial, sans-serif;
  text-align: center;
}

@media (max-width: 900px) {
  .img-slide {
    width: 100%;
  }
  .splide {
    margin-top: 0;
  }
}
</style>

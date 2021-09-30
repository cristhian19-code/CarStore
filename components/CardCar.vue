<template>
  <vs-card :type="type">
    <template #title>
      <h3>{{ card.title }}</h3>
    </template>
    <template #img>
      <img :src="card.url" :alt="card.title" />
    </template>
    <template #text>
      <p>Lorem ipsum dolor sit amet consectetur, adipisicing elit.</p>
    </template>
    <template #interactions>
      <vs-tooltip border dark>
        <vs-button dark icon @click="activeFull()">
          <i class="bx bx-chevrons-right"></i>
        </vs-button>
        <template #tooltip> Ver mas </template>
      </vs-tooltip>

      <vs-button class="btn-chat" primary>
        <i class="bx bx-chat"></i>
        <span class="span"> 54 </span>
      </vs-button>
    </template>
  </vs-card>
</template>

<script>
import { inject } from '@vue/composition-api'
export default {
  props: {
    card:{
      type: Object,
    },
    type: {
      type: String,
      default: '5',
    },
  },
  setup() {
    const activeFullScreen = inject('activeFullScreen')
    const dataDialogCard = inject('dataDialogCard')
    return {
      activeFullScreen,
      dataDialogCard
    }
  },
  methods: {
    activeFull(){
      this.dataDialogCard = this.card
      this.activeFullScreen = !this.activeFullScreen
    }
  },
}
</script>

<style>
.vs-card__img {
  height: 300px;
}
</style>
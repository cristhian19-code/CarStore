<template>
  <vs-dialog v-model="activeFullScreen" overflow-hidden full-screen>
    <template #header>
      <img class="img-details" :src="dataDialogCard.url" alt="">
    </template>
    <template #footer>
      <div class="p-2">
        <div class="display-1 text-center">{{dataDialogCard.name}} - {{dataDialogCard.category}}</div>
        <p>
          Lorem ipsum, dolor sit amet consectetur adipisicing elit. A consequuntur tenetur eligendi repudiandae, dolore optio ratione ipsa quasi ad! Dicta vel unde harum recusandae minus fuga inventore repudiandae earum odio?
          Lorem ipsum, dolor sit amet consectetur adipisicing elit. A consequuntur tenetur eligendi repudiandae, dolore optio ratione ipsa quasi ad! Dicta vel unde harum recusandae minus fuga inventore repudiandae earum odio?
        </p>
        <p><b>Total: </b>S/.{{dataDialogCard.total}}</p>
        <p><b>Cuotas: </b>S/.{{dataDialogCard.cuotas}}</p>
        <div class="d-flex justify-content-center">
          <vs-button dark icon>
            <i class="bx bx-cart"></i>Cotizar
          </vs-button>
        </div>
      </div>
    </template>
  </vs-dialog>
</template>

<script>
import { inject } from '@vue/composition-api'
export default {
  setup() {
    const activeFullScreen = inject('activeFullScreen');
    const dataDialogCard = inject('dataDialogCard');
    return {
      activeFullScreen,
      dataDialogCard
    }
  },
}
</script>

<style scoped>
.img-details{
  height: 250px;
  width: 350px
}

.display-1{
  font-size: 2rem;
}

.text-center{
  text-align: center;
}

.d-flex{
  display: flex
} 
.justify-content-center{
  justify-content: center
}

.p-3{
  padding: 3rem
}

.vs-dialog__content{
  padding: 0;
}
</style>
<template>
  <div class="contact-us">
    <div class="fondo-contact">

    </div>
    <div class="container-contact">
      <div class="content-contact">
        <p>
          Lorem ipsum dolor sit amet, consectetur adipisicing elit. Aperiam nesciunt recusandae quidem. Consectetur, hic iste! Ipsa vel voluptas tenetur rerum ad! Repellat quod quibusdam aliquid earum eaque voluptatum cupiditate obcaecati.
        </p>
      </div>
      <form class="text-white form-contact" action="">
        <p class="text-center display-1">Contactanos</p>
        <div class="my-1">
          <vs-input v-model="name" border success type="text"  label-placeholder="Nombre Completo"></vs-input>
        </div>
        <div class="my-1">
          <vs-input v-model="name" border success type="email"  label-placeholder="Correo"></vs-input>
        </div>
        <div class="my-1">
          <vs-select v-model="value" placeholder="Servicios">
            <vs-option label="Revision" value="1">
              Revision
            </vs-option>
            <vs-option label="Consultas" value="2">
              Consultas
            </vs-option>
            <vs-option label="Cotizacion" value="3">
              Cotizacion
            </vs-option>
            <vs-option label="Reclamos" value="4">
              Reclamos
            </vs-option>
          </vs-select>
        </div>
        <div>
          <textarea class="vs-input" placeholder="Mensaje" rows="10"></textarea>
        </div>
      </form>
    </div>
    <FooterVue />
  </div>
</template>

<script>
import FooterVue from '../../components/Footer.vue'
export default {
  components:{
    FooterVue
  },
  data() {
    return {
      name: '',
      value: 1
    }
  },
}
</script>

<style scoped>
*{
  box-sizing: border-box;
}

.fondo-contact{
  background-image: url(https://images.pexels.com/photos/845451/pexels-photo-845451.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=650&w=940);
  background-position: center bottom;
  background-size: cover;
  background-repeat: no-repeat;
  margin-top: 30px;
  height: 60vh
}

.container-contact{
  width: 100%;
  display: flex;
  justify-content: space-between;
  padding: 0px 20px
}

.contact-us{
  display: flex;
  flex-direction: column;
}

.content-contact{
  width: 200px;
}

.form-contact{
  background-color: #1e1e1e;
  margin-top: -40px;
  border-radius: 15px;
  width: 350px;
  height: 500px;
  display: flex; 
  flex-direction: column;
  padding: 20px;
}

.my-1{
  margin: 1rem 0px;
}

.display-1{
  font-size: 2rem;
}

.display-2{
  font-size: 2.5rem;
}

.display-3{
  font-size: 3rem;
}

.display-4{
  font-size: 3.5rem;
}

.text-white{
  color: white;
}

.text-center{
  text-align: center;
}
</style>
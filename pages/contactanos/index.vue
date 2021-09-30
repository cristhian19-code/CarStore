<template>
  <div class="contact-us">
    <FooterVue />
  </div>
</template>

<script>
import FooterVue from '../../components/Footer.vue'
export default {
    components:{
        FooterVue
    }
}
</script>

<style>
.contact-us{
    display: flex;
    flex-direction: column;
}
</style>
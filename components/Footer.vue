<template>
  <vs-row class="footer">
    <vs-col type="column" w="12" align="center" class="section-footer">
      <img
        src="../assets/1580290827car-race-logo-freesvg.org.svg"
        alt=""
        height="70"
      />
      <p class="font">Ubicacion: Av. Petit Thouars 5356, Int. 1056</p>
      <p class="font">Contacto: (+51) 918955118</p>
      <vs-row justify="center">
        <vs-button circle icon color="rgb(59,89,152)">
          <i class="bx bxl-facebook"></i>
        </vs-button>
        <vs-button circle icon color="rgb(63,114,155)" gradient>
          <i class="bx bxl-instagram"></i>
        </vs-button>
        <vs-button circle icon color="rgb(0,172,238)" gradient>
          <i class="bx bxl-twitter"></i>
        </vs-button>
        <vs-button circle icon color="rgb(37,211,102)" gradient>
          <i class="bx bxl-whatsapp"></i>
        </vs-button>
        <vs-button circle icon color="rgb(0,106,255)" gradient>
          <i class="bx bxl-messenger"></i>
        </vs-button>
        <vs-button circle icon color="rgb(220, 118, 51 )" gradient>
          <i class="bx bx-world"></i>
        </vs-button>
      </vs-row>
      <vs-row justify="center">
        <p>&copy; 2021 - Todos los derechso reservados</p>
      </vs-row>
    </vs-col>
  </vs-row>
</template>

<script>
export default {}
</script>

<style>
.footer {
  display: flex;
  color: white;
  padding: 20px;
  margin-top: 20px;
  background-color: #1e1e1e;
}

.section-footer {
  display: column;
  align-items: center;
}

.font {
  font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande',
    'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
}
</style>
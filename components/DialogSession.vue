<template>
  <vs-dialog v-model="session" blur>
    <template #header>
      <h4 class="not-margin">Welcome to <b>Vuesax</b></h4>
    </template>

    <div v-if="!change" class="con-form">
      <vs-input v-model="input1" placeholder="Email">
        <template #icon> @ </template>
      </vs-input>
      <vs-input v-model="input2" type="password" placeholder="Password">
        <template #icon>
          <i class="bx bxs-lock"></i>
        </template>
      </vs-input>
      <div class="flex">
        <vs-checkbox v-model="checkbox1">Remember me</vs-checkbox>
        <a href="#">Forgot Password?</a>
      </div>
    </div>
    <div v-else class="con-form">
      <vs-input v-model="input1" placeholder="Email">
        <template #icon> @ </template>
      </vs-input>
      <vs-input v-model="input2" type="password" placeholder="Password">
        <template #icon>
          <i class="bx bxs-lock"></i>
        </template>
      </vs-input>
      <vs-input v-model="input2" type="password" placeholder="Password">
        <template #icon>
          <i class="bx bxs-lock"></i>
        </template>
      </vs-input>
      <div class="flex">
        <vs-checkbox v-model="checkbox1">Remember me</vs-checkbox>
        <a href="#">Forgot Password?</a>
      </div>
    </div>
    <template #footer>
      <div class="footer-dialog">
        <vs-button block> Sign In </vs-button>

          <div v-if="!change" class="new">Eres Nuevo <a href="#" @click="change = !change" >Create una cuenta</a></div>
        <div v-else class="new">Ya tienes una cuenta <a href="#" @click="change = !change" >Ingresa</a></div>
      </div>
    </template>
  </vs-dialog>
</template>

<script>
import { inject } from '@vue/composition-api'

export default {
  setup() {
    const session = inject('session')
    return {
      session,
    }
  },
  data() {
    return {
      checkbox1: 0,
      input1: '',
      input2: '',
      change: false
    }
  },
}
</script>

<style scoped>
.con-content {
  display: flex;
  align-items: center;
  justify-content: center;
}
.con-content p {
  margin: 20px 0px;
  position: relative;
  display: block;
  font-size: 0.9rem;
}
.not-margin {
  margin: 0px;
  font-weight: normal;
  padding: 10px;
}
.con-form {
  width: 100%;
}
.con-form .flex {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.con-form .flex a {
  font-size: 0.8rem;
  opacity: 0.7;
}
.con-form .flex a:hover {
  opacity: 1;
}
.con-form .vs-checkbox-label {
  font-size: 0.8rem;
}
.con-form .vs-input-content {
  margin: 10px 0px;
  width: calc(100%);
}

.footer-dialog {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  width: calc(100%);
}
.footer-dialog .new {
  margin: 0px;
  margin-top: 20px;
  padding: 0px;
  font-size: 0.7rem;
}
.footer-dialog .new a {
  color: rgba(var(--vs-primary), 1) !important;
  margin-left: 6px;
}
.footer-dialog .new a:hover {
  text-decoration: underline;
}
.footer-dialog .vs-button {
  margin: 0px;
}

.con-form , .vs-input-content ,.vs-input {
  width: 100% !important;
}

input{
  margin-top: 10px;
}
</style>
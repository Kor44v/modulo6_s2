<template>
  <div id="app">
    <h1>{{saludo}}</h1>
      
      <div class="container">
        <div class="row justify-content-center">
          <div class="col-5 justify-content-center my-5">
            <form action="">
            <div class="mb-3">
              <label for="name" class="form-label">Nombre</label>
              <input v-model="name" type="text" class="form-control" id="name" placeholder="Ingresa tu nombre">
            </div>
            <div class="mb-3">
              <label for="lastName" class="form-label">Apellido</label>
              <input v-model="lastName" type="text" class="form-control" id="lastName" placeholder="Ingresa tu apellido">
            </div>
            <div class="mb-3">
              <label for="email" class="form-label">Correo</label>
              <input v-model="email" type="email" class="form-control" id="email" placeholder="Ingresa tu email">
            </div>
            <div class="mb-3">
              <label for="age" class="form-label">Edad</label>
              <input v-model="age" type="text" class="form-control" id="age" placeholder="Ingresa tu edad">
            </div>
                <button type="submit" @click="alert" class="btn btn-primary">Enviar</button>
            </form>
            <label for="edad">Cual es tu edad?</label>
            <input v-model="edad" type="text" id="edad">
            <div v-if="edad>0&&edad<=13">
                Edad niño
            </div>
            <div v-else-if="edad>14&&edad<=17">
                Edad adolescente 
            </div>
          </div>
        </div>
      </div>
  <form-drilling/>
  </div>
</template>

<script>
import Form from './components/Form.vue'

export default {
  name: 'App',
  data(){
    return{
      saludo:'Formulario',
      name:'',
      lastName:'',
      email:'',
      age:'',
      edad:''

    }
  },
  methods: {
    alert: function(event){
      event.preventDefault();
      alert(`Hola ${this.name} ${this.lastName}, su correo es ${this.email}`)
    }
  },
  components: {
    'form-drilling':Form,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

<template>
  <div class="hello">
    <div class="container">
      <h1>{{ msg }}</h1>
      <form class="text-start">
        <div class="mb-3">
          <label for="nombre" class="form-label">Nombre</label>
          <input type="text" class="form-control" id="nombre" v-model="nombre">
        </div>
        <div class="mb-3">
          <label for="apellido" class="form-label">Apellido</label>
          <input type="text" class="form-control" id="apellido" v-model="apellido">
        </div>
        <div class="mb-3">
          <label for="correo" class="form-label">Correo electrónico</label>
          <input type="email" class="form-control" id="correo" aria-describedby="emailHelp" v-model="correo">
        </div>
        <div class="mb-3">
          <label for="edad" class="form-label">Edad</label>
          <input type="number" class="form-control mb-3" id="edad" v-model="edad">
          <div v-if="edad > 0 && edad < 14">Etapa: niñez</div>
          <div v-else-if="edad > 14 && edad < 18">Etapa: adolescencia</div>
          <div v-else-if="edad > 18 && edad < 36">Etapa: adulto joven</div>
          <div v-else-if="edad > 36 && edad < 65">Etapa: adulto</div>
          <div v-else-if="edad > 65">Etapa: tercera edad</div>
        </div>
        <button @click="enviarDatos" type="button" class="btn btn-primary">Enviar</button>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data: function(){
    return { 
      nombre:"",
      apellido: "",
      correo: "",
      edad: ""
    }
  },
  methods: {
    enviarDatos: function() {
      alert(`Saludos ${this.nombre} ${this.apellido} tu correo es ${this.correo}`)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.hello {
  color: #442072;
}
h1 {
  display: flex;
  justify-content: start;
  margin-bottom: 40px;
}
form {
  width: 350px;
}
</style>

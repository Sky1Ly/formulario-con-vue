<script>
export default {
  name: "App",
  data() {
    return {
      email: "",
      password: "",
      edad: "",
      telefono: "",
      nomRequisitos: ["Dormí 4 horas", "Tomé 8 vasos de agua", "Consumí los nutrientes que me recomendó el nutriologo"]
    }
  }
}
</script>

<template>
  <div>
    <form>
      <div>
        <label>Email:</label>
        <input v-model="email" />
        <p v-show="!email.includes('@')">
          El correo debe incluir un arroba @
        </p>
      </div>

      <div>
        <label>Password:</label>
        <input v-model="password" />
        <p v-show="password.length < 8">
          La contraseña debe contener por lo menos 8 caracteres
        </p>
      </div>

      <div>
        <label>Edad:</label>
        <input v-model="edad" />
        <p v-show="edad < 21">
          Debe tener al menos 21 años
        </p>
      </div>

      <div>
        <label>Telefono:</label>
        <input v-model="telefono" />
        <p v-show="isNaN(telefono)">
          El telefono solo debe contener números
        </p>
      </div>

      <div>
        <label>Requisitos:</label> <br>
        
        <label v-for="nombreRequisito in nomRequisitos" for="">{{ nombreRequisito }} <input type="checkbox" v-show="requerido"/> <br /></label>
      </div>
    </form>
  </div>
</template>

<style>
p {
  color: red;
}
</style>

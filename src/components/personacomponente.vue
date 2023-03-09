<script>
import axios from 'axios'

export default{
    data() {
        return {
            Nombre: " ",
            Edad: "",
            EstadoCivil: " ",
            Trabajo:" ",
            Residencia: " ",
            Cita: " ",
            CitaAutor: " ",
            Bio: " ",
            Personali01: 50,
            Personali02: 50,
            Personali03: 50,
            Personali04: 50,
            Objetivos: " ",
            Frustraciones: [],
            Motivaciones: [],
            Marcas: " ",
        };
    },
    recibe(){
            axios.post("/api/getPersonasUxd.php", {
                nombre: this.Nombre,
                edad: this.Edad,
                estadoCivil: this.EstadoCivil,
                trabajo: this.Trabajo,
                residencia: this.Residencia,
                cita: this.Cita,
                citaAutor: this.CitaAutor,
                bio: this.Bio,
                personalidad01: this.Personali01,
                personalidad02: this.Personali02,
                personalidad03: this.Personali03,
                personalidad04: this.Personali04,
                objetivos: this.Objetivos,
                frustraciones: this.Frustraciones,
                motivaciones: this.Motivaciones,
                marcas: this.Marcas
                //completar las variables, estas deben llamarse como las que se recibirán en el backend sin el símbolo del dolar $
            })
            .then((response) => {
            console.log(response.status)
            });
}
}


</script>

<template>
  <body class="bg-blue-200 font-mono grid grid-cols-2">
    <div class="p-5">
      <label for="buscador" class="font-bold">Buscador</label><br>
      <input type="text" class="form-input border-gray-300 p-5 my-5 rounded-md text-black">
      <div>
        <br>
        <ul class="pl-5">
          <li v-for="p in persona">
            <button @click="recibe(p.id)" class="my-2">{{ p.nombre }}</button>
          </li>
        </ul>
      </div>
      </div>
      <div>
        <div class="p-10 bg-slate-400">
          <h1>Datos personales:</h1>
          <div class="bg-white my-5 mx-8">
            <h1>Datos personales:</h1>
            <h2>Nombre:</h2>
            <h2>Edad:</h2>
            <h2>Estado Civil:</h2>
            <h2>Trabajo:</h2>
            <h2>Residencia:</h2>
          </div>
          <h1>Datos de personsalidad:</h1>
          <div class="bg-red-200 grid gap-5 grid-cols-3 my-5 mx-8">
            <div>
              <h2>Cita:</h2>
              <h2>Autor de la cita:</h2>
            </div>
            <h2>Bio:</h2>
            <div>
              <h2>Personalidad 1:</h2>
              <progress id="file" max="100" value="70"></progress>
              <h2>Personalidad 2:</h2>
              <progress id="file" max="100" value="70"></progress>
              <h2>Personalidad 3:</h2>
              <progress id="file" max="100" value="70"></progress>
              <h2>Personalidad 4:</h2>
              <progress id="file" max="100" value="70"></progress>
            </div>
          </div>
          <h1>Datos de persona</h1>
          <div class="bg-purple-200 my-5 mx-8">
            <ul>Objetivos:
              <li></li>
            </ul>
            <ul>Frustaciones:
              <li></li>
            </ul>
            <ul>Motivaciones:
              <li></li>
            </ul>
            <ul>Marcas:
              <li></li>
            </ul>
          </div>

        </div>
      </div>
  </body>
</template>

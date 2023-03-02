
<script>



</script>

<template>
  <body class="bg-blue-300 font-mono flex">
  <div class="p-5 mx-5">
  <h1 class="my-5 text-xl">Llena el Formulario de sus datos personales</h1>
  <div id="app">
  <form>
    <div class="pl-5 grid gap-5  grid-cols-3 bg-blue-300">
    <div class="my-5">
    <label for="nombre" class="text-lg">Nombre</label><br>
    <input type="text" id="nombre" v-model="nombre" class="form-input border-gray-300 p-2 rounded-md text-black" placeholder="Ingresa nombre">
    </div>
    <div class="my-5">
    <label for="apellido" class="text-lg">Apellido</label><br>
    <input type="text" id="apellido" v-model="apellido" class="form-input border-gray-300 p-2 rounded-md text-black" placeholder="Ingresa apellido">
    </div>
    <div class="my-5">
    <label for="edad" class="text-lg">Edad</label><br>
    <input type="int" id="edad" v-model="edad" class="form-input border-gray-300 p-2 rounded-md text-black" placeholder="Ingresa edad">
    </div>
    <div class="my-5">
    <label for="estadoCivil" class="text-lg">Estado Civil</label><br>
    <select name="estadoCivil" id="estadoCivil" class="form-input border-gray-300 p-2 rounded-md text-black">Selecciona tu estado civil
    <option value="1">Soltero</option>
    <option value="2">Casado</option>
    <option value="3">Divorciado</option>
    <option value="4">Separado</option>
    <option value="5">Union Libre</option>
    <option value="6">Viudo</option>
    </select>
    </div>
    <div class="my-5">
    <label for="trabajo" class="text-lg">Trabajo</label><br>
    <input type="text" id="trabajo" v-model="trabajo" class="form-input border-gray-300 p-2 rounded-md text-black" placeholder="Ingrese su trabajo">
    </div>
    </div>
    <h1 class="my-5 text-xl">Datos de personalidad</h1>
    <div class="pl-5 grid gap-6 grid-cols-3 bg-blue-300">
    <div class="my-5">
    <label for="cita" class="text-md">Escribe una cita</label><br>
    <input type="text" id="cita" v-model="cita" class="form-input border-gray-300 p-2 rounded-md text-black h-full w-full" placeholder="Ingrese una cita">
    </div>
    <div class="my-5">
    <label for="citaAutor" class="text-lg">Autor de la cita</label><br>
    <input type="text" id="citaAutor" v-model="citaAutor" class="form-input border-gray-300 p-2 rounded-md text-black" placeholder="Ingrese autor">
    </div>
    <div class="my-5">
    <label for="bio" class="text-lg">Escribe tu bio</label><br>
    <input type="text" id="bio" v-model="bio" class="form-input border-gray-300 p-2 rounded-md text-black h-full w-full" placeholder="Ingrese tu bio">
    </div>
    <div class="my-5">
    <label for="personalidad01" class="text-lg">Porcentaje de personaliad 1</label><br>
    <input type="int" id="personalidad01" v-model="personalidad01" class="form-input border-gray-300 p-2 rounded-md text-black" placeholder="Ingrese porcentaje">
    </div>
    <div class="my-5">
    <label for="personalidad02" class="text-lg">Porcentaje de personaliad 2</label><br>
    <input type="int" id="personalidad02" v-model="personalidad02" class="form-input border-gray-300 p-2 rounded-md text-black" placeholder="Ingrese porcentaje">
    </div>
    <div class="my-5">
    <label for="personalidad03" class="text-lg">Porcentaje de personaliad 3</label><br>
    <input type="int" id="personalidad03" v-model="personalidad03" class="form-input border-gray-300 p-2 rounded-md text-black" placeholder="Ingrese porcentaje">
    </div>
    <div class="my-5">
    <label for="personalidad04" class="text-lg">Porcentaje de personaliad 4</label><br>
    <input type="int" id="personalidad04" v-model="personalidad04" class="form-input border-gray-300 p-2 rounded-md text-black" placeholder="Ingrese porcentaje">
    </div>
    

    </div>
    <button type="submit" class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 my-5 rounded">Registrar</button>
  </form>
</div>
  </div>
</body>
</template>

<script>



</script>

<template>
  <body class="bg-blue-300 font-mono flex">
  <div class="p-5 mx-5">
  <h1 class="my-5 text-xl">Llena el Formulario de sus datos personales</h1>
  <div id="app">
  <form class="pl-5">
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
    <button type="submit" class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">Registrar</button>
  </form>
</div>
  </div>
</body>
</template>
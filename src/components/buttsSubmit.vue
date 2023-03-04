<script>
export default{
    props:['desactivar']
}

</script>
<template>

<button :disabled="desactivar" class="bg-green-500 disabled:bg-red-500 rounded-lg p-3">

    <slot></slot>
</button>
</template>
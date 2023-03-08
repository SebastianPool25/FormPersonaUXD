<script>
export default{
    props:['desactivar']
}

</script>
<template>

<button class="bg-green-500 disabled:bg-red-500 rounded-lg p-3 my-10">

    <slot></slot>
</button>
</template>
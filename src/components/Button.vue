<template>
    <button :style="{background: color}" class="focus:outline-none hovie btn px-6 py-2 rounded-full text-white">
        {{text}}
    </button>
</template>

<script>
    export default {
        name: 'Button',
        props:{
            text:String,
            color:String
        }
    }

</script>

<style scoped>
    .hovie:hover{
        transform: scale(0.98);
    }
</style>
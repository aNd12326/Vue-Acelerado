<template>
    <h1>{{ texto }}</h1>
</template>

<script>
export default {
    name: 'Titulo',
    props:  {
        texto: String
    }
}
</script>

// scoped para que solo cambie a ese h1 especificado y no globalmente
<style scoped>                  

    h1 {
        color: peru;
    }

</style>
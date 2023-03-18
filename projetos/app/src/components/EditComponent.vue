<template>
    <h1>Editar</h1>
</template>
<script>
export default {
    data() {
        return {
            produto: {}
        }
    },
    created() {
        alert(this.$route.params.id)
    }
}
</script>
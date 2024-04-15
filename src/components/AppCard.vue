
<script>
    export default {
        props: {
            card: Object
    }
}
</script>

<template>
    <div>
        <h3>{{ card.name }}</h3>
        <img :src="card.image" alt="">
    </div>
</template>

<style lang="scss" scoped>

</style>
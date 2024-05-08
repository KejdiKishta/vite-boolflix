<script>
export default {
    props: {
        cardInfo: Object,
    }
}
</script>

<template>
    <div>
        <h3>{{ cardInfo.title }}</h3>
        <h5>{{ cardInfo.original_title }}</h5>
        <div>lang: {{ cardInfo.original_language }}</div>
        <div>Rating: {{ cardInfo.vote_average }}</div>
    </div>
</template>

<style scoped lang="scss">

</style>
<script>
import { store } from "../store.js";
import Card from "./Card.vue"

export default {
    components: {
        Card
    },
    data() {
        return {
            store
        }
    }
}
</script>

<template>
    <div class="container">
        <div class="row">
            <div class="col-sm-6 col-md-4 col-lg-3 my-3" v-for="card in store.moviesArray">
                <Card :cardInfo="card"/>
            </div>
        </div>
        <div class="row">
            <div class="col-sm-6 col-md-4 col-lg-3 my-3" v-for="card in store.TvArray">
                <Card :cardInfo="card"/>
            </div>
        </div>

    </div>
</template>

<style scoped lang="scss">
</style>
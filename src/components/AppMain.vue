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
            <div class="col" v-for="card in store.moviesArray">
                <Card :cardInfo="card"/>
            </div>
        </div>
    </div>
</template>

<style scoped lang="scss">
</style>
<script>
import { store } from '../store';

export default {
    data() {
        return {
            store
        }
    }
}
</script>

<template>
    <div class="container">
        <input type="text" @change="$emit('filter')" placeholder="Es. Interstellar" class="w-50 p-1" v-model="store.query">
        <button type="button" class="btn btn-primary mx-2">Primary</button>
    </div>
</template>

<style scoped lang="scss">

</style>
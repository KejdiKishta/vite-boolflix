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
    <section class="bg-dark">
        <div class="container py-2">
            <div class="row align-items-center">
                <div class="col d-flex align-items-center">
                    <img src="../assets/icons/netflix_png.png" alt="">
                    <h2 class="ms_red fw-bold">BOOLFLIX</h2>
                </div>
                <div class="col text-end">
                    <!-- <input type="text" @change="$emit('filter')" placeholder="Es. Interstellar" class="w-50 p-1" v-model="store.query">
                    <button type="button">Cerca</button> -->
                    <div class="input-wrapper">
                        <button class="icon">
                            <svg
                            width="25px"
                            height="25px"
                            viewBox="0 0 24 24"
                            fill="none"
                            xmlns="http://www.w3.org/2000/svg"
                            >
                                <path
                                    d="M11.5 21C16.7467 21 21 16.7467 21 11.5C21 6.25329 16.7467 2 11.5 2C6.25329 2 2 6.25329 2 11.5C2 16.7467 6.25329 21 11.5 21Z"
                                    stroke="#fff"
                                    stroke-width="1.5"
                                    stroke-linecap="round"
                                    stroke-linejoin="round"
                                ></path>
                                <path
                                    d="M22 22L20 20"
                                    stroke="#fff"
                                    stroke-width="1.5"
                                    stroke-linecap="round"
                                    stroke-linejoin="round"
                                ></path>
                            </svg>
                        </button>
                        <input type="text" name="text" class="input" placeholder="search.." @change="$emit('filter')" v-model="store.query"/>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<style scoped lang="scss">
.ms_red {
    color: red;
}

.input-wrapper {
    display: flex;
    align-items: center;
    justify-content: end;
    gap: 15px;
    position: relative;
}

.input {
    border-style: none;
    height: 50px;
    width: 50px;
    padding: 10px;
    outline: none;
    border-radius: 50%;
    transition: 0.5s ease-in-out;
    background-color: red;
    box-shadow: 0px 0px 3px red;
    padding-right: 40px;
    color: #fff;
}

.input::placeholder,
.input {
    font-family: "Trebuchet MS", "Lucida Sans Unicode", "Lucida Grande", "Lucida Sans", Arial, sans-serif;
    font-size: 17px;
}

.input::placeholder {
    color: #8f8f8f;
}

.icon {
    display: flex;
    align-items: center;
    justify-content: center;
    position: absolute;
    right: 0px;
    cursor: pointer;
    width: 50px;
    height: 50px;
    outline: none;
    border-style: none;
    border-radius: 50%;
    pointer-events: painted;
    background-color: transparent;
    transition: 0.2s linear;
}

.icon:focus ~ .input,
.input:focus {
    box-shadow: none;
    width: 250px;
    border-radius: 0px;
    background-color: transparent;
    border-bottom: 3px solid red;
    transition: all 500ms cubic-bezier(0, 0.11, 0.35, 2);
}
</style>
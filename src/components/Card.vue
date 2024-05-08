<script>
export default {
    props: {
        cardInfo: Object,
    },
    methods: {
        getFlag: function (lang) {
            let flag = "";
            switch (lang) {
                case "it":
                    flag = "italy.png"
                    break;
                case "de":
                    flag = "germany.png"
                    break;
                case "fr":
                    flag = "france.png"
                    break;
                case "es":
                    flag = "spain.png"
                    break;
                case "en":
                    flag = "uk.png"
                    break;
                case "zh":
                    flag = "china.png"
                    break;
                default:
                    flag = "worldwide.png"
                    break;
            }

            return new URL (`../assets/icons/${flag}`, import.meta.url).href;
        }
    }
}
</script>

<template>
    <div class="text-center">
        <h3>{{ cardInfo.title }}</h3>
        <h5>{{ cardInfo.original_title }}</h5>
        <div>
            lang: {{ cardInfo.original_language }}
            <img :src="getFlag(cardInfo.original_language)" alt="">
        </div>
        
        <div>Rating: {{ cardInfo.vote_average }} </div>
    </div>
</template>

<style scoped lang="scss">
img {
    width: 20px;
}
</style>
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
        },
        getThumb: function (img) {
            if (img !== null) {
                return `https://image.tmdb.org/t/p/w342/${img}`
            } else {
                return "https://egress.storeden.net/gallery/59f987adffe48e6f5d6d5016"
            }
        },
        getRating: function(rating) {
            const result = Math.round(rating) / 2
            return Math.ceil(result)
        }
    }
}
</script>

<template>
    <section class="bg-dark">
        <img class="ms_thumb" :src="getThumb(cardInfo.backdrop_path)" :alt="cardInfo.title">
        <div class="text-center m-2 ms_info text-light">
            <div>
                <h5 v-if="cardInfo.title">{{ cardInfo.title }}</h5>
                <h5 v-else>{{ cardInfo.name }}</h5>
    
                <h6 v-if="cardInfo.original_title">{{ cardInfo.original_title }}</h6>
                <h6 v-else>{{ cardInfo.original_name }}</h6>
                
                <div>
                    lang: {{ cardInfo.original_language }}
                    <img :src="getFlag(cardInfo.original_language)" alt="">
                </div>
                
                <div>
                    Rating: 
                    <i 
                    v-for="index in 5" 
                    class="fa-star text-warning" 
                    :class="getRating(cardInfo.vote_average) < index ? 'fa-regular' : 'fa-solid'">
                    </i> 
                </div>
            </div>
            <!-- <div>Rating: {{ getRating(cardInfo.vote_average) }} </div> -->
        </div>
    </section>
</template>

<style scoped lang="scss">
.ms_thumb {
    height: 100%;
}

section{
    aspect-ratio: 1;
    border: 2px solid white;

    &:hover {
        .ms_info {
            display: block;
        };
        .ms_thumb {
            display: none;
        }
    }

    .ms_info {
        display: none;
        img {
            width: 20px;
        }
    }
}
</style>
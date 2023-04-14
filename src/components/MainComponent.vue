<template>
    <main>
        <div class="main-top">
            <div class="container">
                <p class="m-0 text-light py-5">Content goes here</p>
            </div>
        </div>
        <div class="main-bottom text-uppercase py-5 text-light">
            <div class="container d-flex justify-content-between">
                <div v-for="card in cards" class="d-flex align-items-center">
                    <img :src="getImagePath(`../assets/images/${card.url}`)" alt="">
                    <p class="m-0">{{ card.text }}</p>
                </div>
            </div>
        </div>
    </main>
    <div>
    </div>
</template>

<script>
import {items} from '../data/data.js'
export default {
    name: 'FooterComponent',
    data(){
        return{
            cards: items
        }
    },
    methods: {
        getImagePath: function(imgPath){
            return new URL(imgPath, import.meta.url).href;
        }
    }
}
</script>

<style lang="scss" scoped>
    *{
        font-family: 'Oswald', sans-serif;
    }
    .main-top{
        background-color: black;
    }
    .main-bottom{
        background-color: #0282f9;
        font-size: 15px;
        img{
            width: 55px;
            height: 45px;
            object-fit: contain;
            margin: 0px 10px;
        }
    }
</style>
<template>
    <main>
        <div class="jumbo overflow-hidden">
            <img class="img-fluid" src="../assets/images/jumbotron.jpg" alt="Jumbotron">
        </div>
        <div class="main-top p-5">
            <div class="container">
                <div class="row">
                    <CardComponent :image="film.thumb" :title="film.series" v-for="film in films"/>
                </div>
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
import {items} from '../data/data.js';
import {cards} from '../data/data.js';
import CardComponent from './CardComponent.vue';

export default {
    name: 'FooterComponent',
    components: {
        CardComponent
    },
    data(){
        return{
            cards: items,
            films: cards
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
    .jumbo{
        width: 100%;
        height: 350px;
    }
</style>
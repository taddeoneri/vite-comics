<template>
    <footer>
        <div class="footer-top">
            <div class="container d-flex justify-content-between align-items-center">
                <div class="d-flex">
                    <ul class="text-light m-0 p-0" v-for="(list, index) in lists">
                        <li><h4 class="my-3">{{ list.title }}</h4></li>
                        <li class="text-capitalize" v-for="(link, index) in list.items"><a :href="link.url">{{ link.text }}</a></li>
                    </ul>
                </div>
                <div class="box-image">
                    <img src="../assets/images/dc-logo-bg.png" alt="">
                </div>
            </div>
        </div>
        <div class="footer-bottom py-3">
            <div class="container d-flex justify-content-between align-items-center">
                <button>Sign-up now!</button>
                <div class="d-flex align-items-center">
                    <p class="m-0">Follow us</p>
                    <div class="d-flex">
                        <img v-for="picture in pictures" :src="'/images/'+picture.name" alt="">
                    </div>
                </div>
            </div>
            
        </div>
    </footer>
</template>

<script>
import {menu} from '../data/data.js';
import {images} from '../data/data.js';

export default {
    name: 'MainComponent',
    data(){
        return{
            lists: menu,
            pictures: images
        }
    }
}
</script>

<style lang="scss" scoped>
    .footer-top{
        background-image: url('../assets/images/footer-bg.jpg');
        background-size: cover;
    }
    .footer-bottom{
        background-color: darkgray;
    }
    img{
        opacity: .5;
    }
    li{
        list-style: none;
        a{
            text-decoration: none;
            color: white;
            font-size: 14px;
        }
    }
    h4{
        text-transform: uppercase;
    }
</style>
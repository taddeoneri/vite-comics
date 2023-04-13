<template>
    <footer>
        <div class="container">
            <ul class="text-light" v-for="(list, index) in lists">
                <li>{{ list.title }}</li>
                <li v-for="(link, index) in list.items"><a :href="link.url">{{ link.text }}</a></li>
            </ul>
        </div>
        <div class="container d-flex justify-content-between align-items-center">
            <button>Sign-up now!</button>
            <div class="d-flex align-items-center">
                <p class="m-0">Follow us</p>
                <div class="d-flex">
                    <img v-for="picture in pictures" src="../assets/images/footer-facebook.png" alt="">
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
    footer{
        background-image: url('../assets/images/footer-bg.jpg');
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
</style>
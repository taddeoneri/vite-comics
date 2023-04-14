<template>
    <footer>
        <div class="footer-top overflow-hidden">
            <div class="container d-flex justify-content-between align-items-center">
                <div class="d-flex">
                    <ul class="text-light p-0" v-for="(list, index) in lists">
                        <li><h4 class="my-3">{{ list.title }}</h4></li>
                        <li class="text-capitalize" v-for="(link, index) in list.items"><a :href="link.url">{{ link.text }}</a></li>
                    </ul>
                </div>
                <div class="box-image">
                    <img src="../assets/images/dc-logo-bg.png" alt="">
                </div>
            </div>
        </div>
        <div class="footer-bottom py-4">
            <div class="container d-flex justify-content-between align-items-center">
                <button>Sign-up now!</button>
                <div class="d-flex align-items-center">
                    <p class="m-0 text-primary text-uppercase fw-bold mx-2">Follow us</p>
                    <div class="d-flex">
                        <img class="ms-3" v-for="picture in pictures" :src="'/images/'+picture.name" alt="">
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
        .container{
            height: 430px;
        }
        ul{
            margin-right: 30px;
        }
    }
    .footer-bottom{
        background-color: #303030;
        p{
            font-size: 18px;
        }
        button{
            border: 2px solid #0d6efd;
            background-color: #303030;
            color: white;
            text-transform: uppercase;
            padding: 8px 12px;
            font-size: 15px;

        }
    }
    li{
        list-style: none;
        a{
            text-decoration: none;
            color: #949494;
            font-size: 14px;
        }
    }
    h4{
        text-transform: uppercase;
    }
</style>
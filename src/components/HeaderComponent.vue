<template>
    <header class="bg-light text-uppercase py-3">
        <div class="container bg-light d-flex justify-content-between align-items-center">
            <div>
                <img src="../assets/images/dc-logo.png" alt="Logo">
            </div>
            <ul class="d-flex m-0">
                <li v-for="(product, index) in products" class="ms-4">{{ product.text }}<a :href="product.url"></a></li>
            </ul>
        </div>
    </header>
</template>

<script>
import {section} from '../data/data.js';
export default {
    name: 'HeaderComponent',
    data(){
        return{
            products: section
        }
    }
}
</script>

<style lang="scss" scoped>
    li{
        list-style: none;
        a{
            text-decoration: none;
        }
    }
    img{
        width: 80px;
        height: 80px;
    }   
</style>
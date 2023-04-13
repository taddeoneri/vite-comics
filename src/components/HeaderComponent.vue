<template>
    <div>
        <img src="../assets/images/dc-logo.png" alt="Logo">
    </div>
    <ul>
        <li v-for="(product, index) in products">{{ product.text }}<a :href="product.url"></a></li>
    </ul>
</template>

<script>
import {section} from '../data/data.js'
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

</style>
<template>
    <div class="col-12 col-sm-6 col-md-4 col-lg-2">
        <div class="mycard m-0">
            <img :src="image" class="img-fluid" :alt="title">
        </div>
        <div>
            <p class="text-uppercase text-light">{{title}}</p>
        </div>
    </div>
</template>

<script>
export default {
    name: 'CardComponent',
    props: {
        image: String,
        title: String
    }
}
</script>

<style lang="scss" scoped>
    .mycard{
        width: 140px;
        height: 140px;
        overflow: hidden;
    }
    p{
        font-size: 13px;
        padding: 15px 0px 20px 0px;
    }
</style>
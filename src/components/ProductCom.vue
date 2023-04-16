<template>
    <div class="parent" :style="{'height': props.ProductComData.productComHeight, 'top': props.ProductComData.productComTop}">
        <div class="title">
            OUR INGRADIENTS
        </div>
        <div style="display: flex;flex-direction: row;">
            <div class="wave"></div>
            <div class="wave"></div>
        </div>
        <div class="row content">
            <div class="col-8">
                Cras quis nulla commodo, aliquam lectus sed, blandit augue. Cras ullamcorper bibendum bibendum. Duis tincidunt urna non pretium porta. Nam condimentum vitae ligula vel ornare. Phasellus at semper turpis. Nunc eu tellus tortor. Etiam at condimentum nisl, vitae sagittis orci. Donec id dignissim nunc. Donec elit ante, eleifend a dolor et, venenatis facilisis dolor. In feugiat orci odio, sed lacinia sem elementum quis. Aliquam consectetur, eros et vulputate euismod, nunc leo tempor lacus, ac rhoncus neque eros nec lacus. Cras lobortis molestie faucibus.
            </div>
        </div>
        <MoreBtn class="more-btn" :data="moreBtnData"></MoreBtn>
        <div class="row">
            <div v-for="(contentData, index) in content" :key="index"
                class="col-4 product-content">
                <ProductContent :data="contentData"></ProductContent>
            </div>
        </div>
        <div class="end">
            VIEW MORE DIGISALAD’S INGRADIENTS
        </div>
    </div>
</template>

<script lang="ts" setup>
import MoreBtn from './btn/MoreBtn.vue';
import ProductContent from './ProductContent.vue';
import { defineProps, ref } from 'vue';

const props = defineProps<{
    ProductComData:{
        productComHeight: string,
        productComTop: string
    }
}>();
const moreBtnData = ref<{width: string, height: string, title: string, color: string}>({width: '15%', height: '3%', title: 'OUR SERVICES', color: '#585880'});
const content = ref<{title: string, imgSrc: string, btnContent: string}[]>([
    {
        title: 'UX Design',
        imgSrc: require('@/assets/img1.svg'),
        btnContent: 'VIEW MORE'
    },
    {
        title: 'UX Design',
        imgSrc: require('@/assets/img2.svg'),
        btnContent: 'VIEW MORE'
    },
    {
        title: 'website development',
        imgSrc: require('@/assets/img3.svg'),
        btnContent: 'VIEW MORE'
    },
    {
        title: 'mobile app development',
        imgSrc: require('@/assets/img4.svg'),
        btnContent: 'VIEW MORE'
    },
    {
        title: 'ecommerce',
        imgSrc: require('@/assets/img5.svg'),
        btnContent: 'VIEW MORE'
    },
    {
        title: 'customer loyalty',
        imgSrc: require('@/assets/img6.svg'),
        btnContent: 'VIEW MORE'
    },
    {
        title: 'digital transformation',
        imgSrc: require('@/assets/img7.svg'),
        btnContent: 'VIEW MORE'
    },
    {
        title: 'digital marketing',
        imgSrc: require('@/assets/img8.svg'),
        btnContent: 'VIEW MORE'
    },
    {
        title: 'BRANDING',
        imgSrc: require('@/assets/img9.svg'),
        btnContent: 'BRANDING'
    }]);
</script>

<style lang="scss" scoped>
.row{
    width: 80%;
    justify-content: center;
}
.parent{
    position: relative;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    width: 100%;
    border-radius: 30px;
    color: #FFFFFF;
    background: #26C6D0;
    z-index: var(--window-page);

    div{
        display: flex;
    }
}

.title{
    font-size: 28px;
}

.wave{
    height: 15px;
    background: #585880;
}

.content{
    margin-top: 3%;
    margin-bottom: 3%;
}

.more-btn{
    margin-bottom: 3%;
}

.product-content{
    margin-bottom: 5%;
}

.end{
    text-decoration:underline;
    text-decoration-thickness: 5px;
    text-decoration-color: #FFBC58;
}
</style>
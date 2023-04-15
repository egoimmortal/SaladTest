<template>
    <div ref="componentParent" class="container abort-container">
        <h4 class="row title">ABOUT DIGISALAD</h4>
        <h4 class="wave"></h4>
        <div class="row video-container">
            <VideoCom :src="videoSrc"></VideoCom>
        </div>
        <div class="row">
            <h5 class="col-8 offset-2 info">
                Cras quis nulla commodo, aliquam lectus sed, blandit augue. Cras ullamcorper bibendum bibendum. Duis tincidunt urna non pretium porta. Nam condimentum vitae ligula vel ornare. Phasellus at semper turpis. Nunc eu tellus tortor. Etiam at condimentum nisl, vitae sagittis orci. Donec id dignissim nunc. Donec elit ante, eleifend a dolor et, venenatis facilisis dolor. In feugiat orci odio, sed lacinia sem elementum quis. Aliquam consectetur, eros et vulputate euismod, nunc leo tempor lacus, ac rhoncus neque eros nec lacus. Cras lobortis molestie faucibus.
            </h5>
        </div>
        <div class="more">
            <span>VIEW MORE</span>
        </div>
    </div>
</template>

<script lang="ts" setup>
import VideoCom from '@/components/VideoCom.vue';
import { onMounted, ref } from 'vue';

const componentParent = ref();
const videoSrc = ref('https://www.youtube.com/embed/IeIRJ9jZ5Ro?rel=0&enablejsapi=1&widgetid=1');

onMounted(() => {
    console.log('window.clientHeight = ', window.innerHeight);
    console.log('componentParent = ', componentParent.value.offsetHeight);

    Resize();

    window.addEventListener('resize', Resize);
});

function Resize(){
    componentParent.value.style.height = window.innerHeight * 1.3 + 'px';
}
</script>

<style lang="scss" scoped>
.abort-container{
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    background-color: #E5E5E5;
}

.row.title{
    position: relative;
    margin-bottom: 0px;

    &.title:after{
        font-size: 50px;
        color: #ee6c8a;
        content: ".";
        position: absolute;
        right: -10%;
        bottom: -6px;
    }
}

.video-container{
    width: 67%;
    height: 35%;
    margin-top: 9%;
}

.info{
    margin-top: 5%;
    margin-bottom: 5%;
    padding: 0px;
}

.more{
    position: relative;
    width: 223px;
    height: 86px;
    background: #26C6D0;
    border-radius: 1px;
    color: #FFFFFF;
    display: flex;
    justify-content: center;
    align-items: center;

    span{
        position: absolute;
        left: 15%;
    }
    span:after{
        content: "";
        width: 50%;
        height: 10%;
        font-style: solid;
        top: 0px;
        position: absolute;
        left: 95px;
        background-color: #FFFFFF;
        transform: translate(10px, 10px);
    }
}
</style>
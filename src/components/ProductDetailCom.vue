<template>
    <div class="parent" :style="{'height': props.PoductDetialComData.PoductDetialComHeight, 'top': props.PoductDetialComData.productComTop}">
        <div class="parent-bg"></div>
        <div class="parent-content">
            <div class="left-page-btn page-btn">
                <img src="@/assets/left.png">
            </div>
            <img class="info-img" src="@/assets/LP_fb_01.png" />
            <div class="info">
                <div class="info-head">
                    HIGHLIGHTED SHOWCASE
                </div>
                <h2 class="info-title pink-dot">
                    LP CLUB MOBILE APP
                </h2>
                <div class="info-content">
                    Cras quis nulla commodo, aliquam lectus sed, blandit augue. Cras ullamcorper bibendum bibendum. Duis tincidunt urna non pretium porta. Nam condimentum vitae ligula vel ornare. Phasellus at semper turpis. Nunc eu tellus tortor. Etiam at condimentum nisl, vitae sagittis orci. Donec id dignissim nunc. Donec elit ante, eleifend a dolor et, venenatis facilisis dolor. In feugiat orci odio, sed lacinia sem elementum quis. Aliquam consectetur, eros et vulputate euismod, nunc leo tempor lacus, ac rhoncus neque eros nec lacus. Cras lobortis molestie faucibus.
                </div>
            </div>
            <div class="right-page-btn page-btn">
                <img src="@/assets/right.png">
            </div>
            <div class="page-number-parent">
                <span>01</span>
                <span>04</span>
            </div>
        </div>
        <MoreBtn :data="moreBtnData" :style="{'top': '-50px'}"></MoreBtn>
    </div>
</template>

<script lang="ts" setup>
import MoreBtn from './btn/MoreBtn.vue';
import { defineProps, ref } from 'vue';

const props = defineProps<{
    PoductDetialComData:{
        PoductDetialComHeight: string,
        productComTop: string
    }
}>();
const moreBtnData = ref<{width: string, height: string, title: string, color: string}>({width: '300px', height: '150px', title: 'VIEW PROJECT', color: '#26C6D0'});
</script>

<style lang="scss" scoped>
.parent{
    position: relative;
    border-radius: 0px 0px 30px 30px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    color: #FFFFFF;
    
    *{
        position: relative;
    }

    .parent-bg{
        background: linear-gradient(0deg, rgba(0, 0, 0, 0.75), rgba(0, 0, 0, 0.75)), url('@/assets/LP_fb_01.png');
        background-blend-mode: normal, multiply;
        background-size: cover;
        filter: blur(10px);
        position: absolute;
        left: 0px;
        top: 0px;
        width: 100%;
        height: 100%;
    }

    .parent-content{
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .info-img{
        width: 37%;
        margin-left: 3%;
        margin-right: 3%;
    }

    .info{
        width: 29%;
        margin-right: 3%;
        text-align: left;

        .info-head{
            margin-bottom: 5%;
            line-height: 19px;
            letter-spacing: 2.2px;
        }

        .info-title{
            margin-bottom: 5%;
            line-height: 39px;
            letter-spacing: 3.6px;
            text-decoration: underline;
            text-decoration-thickness: 5px;
            text-decoration-color: #26C6D0;
        }

        .pink-dot:after{
            right: 0%;
            bottom: 0px;
        }
    }

    .page-btn{
        background-color: #26C6D0;
        border-radius: 50%;
        width: 53px;
        height: 53px;
        display: flex;
        justify-content: center;
        align-items: center;

        img{
            height: 50%;
        }
    }

    .page-number-parent{
        position: absolute !important;
        right: 10% !important;
        top: -5% !important;
        width: 34px;
        height: 34px;

        &:after{
            content: '-';
            display: inline-block;
            width: 100%;
            height: 1%;
            bottom: 50%;
            color: rgba(0,0,0,0);
            background-color: #26C6D0;
            position: absolute;
            left: 0px;
            transform: rotate(135deg);
        }

        & span:first-child{
            position: absolute;
            left: -25%;
            top: -25%;
        }

        & span:last-child{
            position: absolute;
            right: -25%;
            bottom: -25%;
        }
    }
}
</style>
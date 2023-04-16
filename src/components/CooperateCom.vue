<template>
    <div class="parent" :style="{'height': props.CooperateData.CooperateComHeight, 'top': props.CooperateData.productComTop}">
        <div class="title">OUR BRAND EXPERIENCE</div>
        <div class="wave-parent">
            <div class="wave"></div>
            <div class="wave"></div>
            <div class="wave"></div>
        </div>
        <div class="content">
            Cras quis nulla commodo, aliquam lectus sed, blandit augue. Cras ullamcorper bibendum bibendum. Duis tincidunt urna non pretium porta. Nam condimentum vitae ligula vel ornare. Phasellus at semper turpis. Nunc eu tellus tortor. Etiam at condimentum nisl, vitae sagittis orci. Donec id dignissim nunc. Donec elit ante, eleifend a dolor et, venenatis facilisis dolor. In feugiat orci odio, sed lacinia sem elementum quis. Aliquam consectetur, eros et vulputate euismod, nunc leo tempor lacus, ac rhoncus neque eros nec lacus. Cras lobortis molestie faucibus.
        </div>
        <img src="@/assets/img12.png" />
    </div>
</template>

<script lang="ts" setup>
import { defineProps } from 'vue';

const props = defineProps<{
    CooperateData:{
        CooperateComHeight: string,
        productComTop: string
    }
}>();
</script>

<style lang="scss" scoped>
.parent{
    position: relative;
    padding-top: 20%;
    padding-left: 15%;
    padding-right: 15%;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    background-color: #FFFFFF;

    .title{
        font-size: 28px;
        line-height: 34px;
        letter-spacing: 3.63636px;
    }

    .wave-parent{
        display: flex;
    }

    .content{
        margin-top: 7%;
        margin-bottom: 7%;
    }

    img{
        width: 100%;
    }
}
</style>
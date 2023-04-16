<template>
    <div class="parent">
        <img :src="props.data.imgSrc"/>
        <span class="title">{{  props.data.title }}</span>
        <span class="content">
            <h6>
                Cras quis nulla commodo, aliquam lectus sed, blandit augue. Cras ullamcorper bibendum bibendum. Duis tincidunt urna non pretium porta. Nam condimentum vitae ligula vel ornare.
            </h6>
        </span>
        <div class="btn">
            <span>{{ props.data.btnContent }}</span>
        </div>
    </div>
</template>

<script lang="ts" setup>
import { defineProps } from 'vue';
const props = defineProps<{
    data:{
        title: string,
        imgSrc: string,
        btnContent: string
    }
}>();
</script>

<style lang="scss" scoped>
.parent{
    border-radius: 50px;
    border-color: #FFFFFF;

    *{
        color: #FFFFFF;
    }

    .content{
        margin-top: 5%;
        margin-bottom: 5%;
    }

    .btn{
        border: 1px #FFFFFF solid;
        border-radius: 50px;
    }
}
</style>
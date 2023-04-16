<template>
    <div class="more" :style="{width: props.data.width, height: props.data.height, background: props.data.color}">
        <span>{{ props.data.title }}</span>
    </div>
</template>

<script lang="ts" setup>
import { defineProps } from 'vue';

const props = defineProps<{
    data:{
        width: string,
        height: string,
        title: string,
        color: string
    }
}>();
</script>

<style lang="scss" scoped>
.more{
    position: relative;
    // width: 223px;
    // height: 86px;
    background: #26C6D0;
    border-radius: 1px;
    color: #FFFFFF;
    display: flex;
    justify-content: center;
    align-items: center;

    span{
        position: absolute;
        left: 5%;
        width: 60%;
    }
    span:after{
        content: "";
        width: 50%;
        height: 10%;
        top: 0px;
        position: absolute;
        left: 90%;
        background-color: #FFFFFF;
        transform: translate(10px, 10px);
    }
}
</style>
<template>
    <div ref="componentParent" class="right-info-parent" :style="{'width': props.props.rightInfoWidth, 'height': props.props.rightInfoHeight}">
        <div class="row">
            <div class="col-4 left-side offset-1">
                <div class="title pink-dot">
                    <h3>
                        AWARDS
                    </h3>
                </div>
                <div class="wave"></div>
                <div class="content">
                    <h5>
                        Cras quis nulla commodo, aliquam lectus sed, blandit augue. Cras ullamcorper bibendum bibendum. Duis tincidunt urna non pretium porta. Nam condimentum vitae ligula vel ornare. Phasellus at semper turpis. Nunc eu tellus tortor. Etiam at condimentum nisl, vitae sagittis orci. Donec id dignissim nunc. 
                    </h5>
                </div>
            </div>
            <div class="col-6 right-side">
                <div class="row">
                    <div v-for="index in 4" :key="index" class="col-6">
                        <img src="@/assets/test.svg">
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script lang="ts" setup>
import { defineProps } from 'vue';

const props = defineProps<{
    props:{
        rightInfoWidth: string,
        rightInfoHeight: string
    }
}>();
</script>

<style lang="scss" scoped>
div{
	position: relative;
}

.row{
    width: 100%;
}

.left-side{
    display: flex;
    justify-content: flex-start;
    flex-direction: column;
    align-items: flex-start;
}

.title{
    position: relative;
    left: 22px;
}
.content{
    text-align: left;
    margin-top: 31px;
}

.right-info-parent{
    position: absolute;
    right: 0px;
    display: flex;
    justify-content: space-around;
    align-items: center;
    border-radius: 30px 0px 30px 30px;
    background-color: #FFFFFF;
}
</style>
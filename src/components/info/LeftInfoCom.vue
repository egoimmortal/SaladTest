<template>
    <div class="left-info-parent" :style="{'width': props.props.infoWidth, 'height': props.props.infoHeight, 'top': props.props.productComTop}">
        <div class="row">
            <div class="col-4 left-side">
                <img src="@/assets/img10.png" />
                <h4>Tony Ng</h4>
                <h5>Founder & Creative Director</h5>
            </div>
            <div class="col-7 right-side">
                <div>
                    <img src="@/assets/img11.png" />
                    <img src="@/assets/img11.png" />
                </div>
                <h4 class="right-side-content">
                    A great digital work isn’t about designing beautiful pages purely. It is about context - how do we deliver the 
                    <span class="orange">right experience to the right person at the right time. </span>
                    The most important thing is that your work can engage customers at anytime, anywhere and let users experience an entire amazing digital journey.
                </h4>
            </div>
        </div>
    </div>
</template>

<script lang="ts" setup>
import { defineProps } from 'vue';

const props = defineProps<{
    props:{
        infoWidth: string,
        infoHeight: string,
        productComTop: string
    }
}>();
</script>

<style lang="scss" scoped>
div{
	position: relative;
}
img{
    height: 80%;
    border-radius: 50%;
}

.row{
    width: 100%;
    height: 100%;

    & > div{
        height: 100%;
    }
}

.left-info-parent{
    position: relative;
    left: 0px;
    display: flex;
    justify-content: space-around;
    align-items: center;
    color: #FFFFFF;
    border-radius: 0px 30px 30px 30px;
    background-color: #585880CC;
    z-index: var(--window-info);

    .row{
        display: flex;
        align-items: center;
    }
}

.left-side{
    height: 50% !important;

    *:first-child{
        margin-bottom: 10%;
    }
}

.right-side{
    height: 70% !important;

    div{
        display: flex;
        align-items: center;
        justify-content: center;
    }
}

.right-side-content{
    margin-top: 26px;
    line-height: 48px;
    letter-spacing: 2px;
    font-size: 22px;

    .orange{
        color: #FFBC58;
    }
}
</style>
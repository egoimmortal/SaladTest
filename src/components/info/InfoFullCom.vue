<template>
    <div class="parent" :class="{'open': props.show, 'close': !props.show}">
        <div class="left-side">
            <div class="top">
                <img src="@/assets/icon1.png" />
                <div class="btn-content">
                    <span>EMPOWERING BRANDS</span>
                    <span class="pink-dot">ABOUT US</span>
                </div>
            </div>
            <div class="down">
                <img src="@/assets/icon2.png" />
                <div class="btn-content">
                    <span>CASE STUDIES</span>
                    <span class="pink-dot">WORKS</span>
                </div>
            </div>
        </div>
        <div class="middle-side">
            <div class="top">
                <img src="@/assets/icon3.png" />
                <div class="btn-content">
                    <span>BE COOL WITH US</span>
                    <span class="pink-dot">CAREERS</span>
                </div>
            </div>
            <div class="down">
                <img src="@/assets/icon4.png" />
                <div class="btn-content">
                    <span>OUR STRATEGIES</span>
                    <span class="pink-dot">INSIGHTS</span>
                </div>
            </div>
        </div>
        <div class="right-side">
            <div class="top">
                <img src="@/assets/icon5.png" />
                <div class="btn-content">
                    <span>AREAS OF EXPERTISE</span>
                    <span class="pink-dot">SERVICES</span>
                </div>
            </div>
            <div class="down">
                <div class="btn-content">
                    <span>START YOUR JOURNEY WITH US</span>
                    <span class="pink-dot">CONTACT</span>
                </div>
            </div>
        </div>
    </div>
</template>

<script lang="ts" setup>
import { defineProps } from 'vue';
const props = defineProps<{
    show: boolean
}>();
</script>

<style lang="scss" scoped>
.parent{
    position: absolute;
    top: 0px;
    left: 0px;
    width: 100%;
    height: 100%;
    display: none;
    justify-content: space-evenly;
    align-items: center;
    color: #FFFFFF;
    background: linear-gradient(180deg, #585880 3.61%, #26C6D0 95.7%);
    z-index: var(--window-full-info-page);

    &.open{
        display: flex !important;
    }

    &.close{
        display: none !important;
    }

    & > div{
        display: flex;
        flex-direction: column;
        justify-content: space-evenly;
        align-items: center;
        height: 100%;

        & > div{
            width: 100%;
            border-radius: 30px;
        }
    }

    .left-side{
        width: 30%;
        .top{
            background: linear-gradient(0deg, rgba(113, 246, 255, 0.7), rgba(113 246 255 / 70%)), url('@/assets/infoFull1.png');
            background-size: contain;
            height: 25%;
            display: flex;
            flex-direction: row;
            justify-content: space-evenly;
            align-items: center;

            div{
                align-items: flex-start;
            }
            img{
                height: 30%;
            }
            span.pink-dot:after{
                bottom: 35%;
            }
        }
        .down{
            background: linear-gradient(0deg, rgba(247, 146, 146, 0.7), rgba(247, 146, 146, 0.7)), url('@/assets/infoFull2.png');
            background-size: cover;
            height: 40%;
            display: flex;
            flex-direction: row;
            justify-content: flex-start;
            align-items: flex-end;

            *{
                bottom: 15%;
                left: 10%;
            }
            img{
                position: relative;
                height: 20%;
            }

            span.pink-dot:after{
                color: #26C6D0;
            }
        }
    }

    .middle-side{
        width: 20%;

        & > div{
            display: flex;
            justify-content: flex-end;
            align-items: center;
            flex-direction: column;
        }
        .top{
            background: linear-gradient(0deg, rgba(255 201 121 / 60%), rgba(255 201 121 / 60%)), url('@/assets/infoFull3.png');
            background-size: cover;
            height: 50%;

            *{
                bottom: 10%;
                left: -7%;
            }

            img{
                position: relative;
                height: 10%;
                bottom: 15%;
                left: -20%;
            }
        }
        .down{
            background: linear-gradient(0deg, rgb(98 255 182 / 25%), rgba(98 255 182 / 25%)), url('@/assets/infoFull4.png');
            background-size: cover;
            height: 30%;
            display: flex;
            align-items: flex-start;
            justify-content: center;

            *{
                left: 7%;
            }
            img{
                position: relative;
                height: 30%;
                left: 10%;
            }
            div{
                margin-top: 5%;
                align-items: flex-start;
            }
        }
    }

    .right-side{
        width: 27%;
        .top{
            background: linear-gradient(0deg, rgb(113 78 255 / 25%), rgb(113 78 255 / 25%)), url('@/assets/infoFull5.png');
            background-size: contain;
            height: 35%;
            display: flex;
            flex-direction: column;
            align-items: flex-start;
            justify-content: flex-end;

            *{
                bottom: 15%;
                left: 7%;
                align-items: flex-start;
                margin-top: 5%;
            }
            img{
                position: relative;
                height: 25%;
                left: 10%;
            }
        }
        .down{
            color: #000000;
            background-color: #FFFFFF;
            height: 25%;
            display: flex;
            align-items: center;
            justify-content: center;

            div{
                align-items: flex-start;
            }

            span.pink-dot{
                color: #26C6D0;
            }
        }
    }
}

.btn-content{
    position: relative;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;

    *{
        position: relative;
    }

    span{
        font-size: 16px;
        line-height: 19px;
        letter-spacing: 1.8px;
        margin-top: 5%;
    }

    span.pink-dot{
        font-size: 32px;
        line-height: 39px;
        letter-spacing: 3.63636px;
    }

    span.pink-dot:after{
        font-size: 80px;
        bottom: 42%;
        right: -15%;
    }
}
</style>
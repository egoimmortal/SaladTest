<template>
	<div class="home">
		<VideoCom :src="videoSrc"></VideoCom>
		<AbortCom :AbortComHeight="AbortComHeight"></AbortCom>
		<RightInfoCom :props="RightInfoComData"></RightInfoCom>
		<ProductCom :ProductComData="ProductComData"></ProductCom>
		<LeftInfoCom :props="LeftInfoComData"></LeftInfoCom>
		<CooperateCom :CooperateData="CooperateComData"></CooperateCom>
		<ProductDetailCom :PoductDetialComData="PoductDetialComData"></ProductDetailCom>
	</div>
</template>

<script lang="ts" setup>
import VideoCom from '@/components/VideoCom.vue';
import AbortCom from '@/components/AbortCom.vue';
import RightInfoCom from '@/components/info/RightInfoCom.vue';
import ProductCom from '@/components/ProductCom.vue';
import LeftInfoCom from '@/components/info/LeftInfoCom.vue';
import CooperateCom from '@/components/CooperateCom.vue';
import ProductDetailCom from '@/components/ProductDetailCom.vue';

import { onMounted, ref } from 'vue';

const videoSrc = ref('https://www.youtube.com/embed/8_4JRK4QkqU?autohide=0&branding=0&controls=0&showinfo=0&autoplay=1&mute=1&rel=0&enablejsapi=1&widgetid=1');
const AbortComHeight = ref('0px');
const RightInfoComData = ref<{infoWidth: string, infoHeight: string}>({infoWidth: '0px',infoHeight: '0px'});
const ProductComData = ref<{productComHeight: string, productComTop: string}>({productComHeight: '0px',productComTop: '0px'});
const LeftInfoComData = ref<{infoWidth: string, infoHeight: string, productComTop: string}>({infoWidth: '0px',infoHeight: '0px', productComTop: '0px'});
const CooperateComData = ref<{CooperateComHeight: string, productComTop: string}>({CooperateComHeight: '0px', productComTop: '0px'});
const PoductDetialComData = ref<{PoductDetialComHeight: string, productComTop: string}>({PoductDetialComHeight: '0px', productComTop: '0px'});

onMounted(() => {
	Resize();

    window.addEventListener('resize', Resize);
});

function Resize(){
	let infoWidth = window.innerWidth * 0.93 + 'px';
	let infoHeight = window.innerHeight * 0.4 + 'px';
	let productComHeight = window.innerHeight * 2.3 + 'px';
	let productComTop = window.innerHeight * 0.2 + 'px';
	let CooperateComHeight = window.innerHeight * 1.5 + 'px';
	let PoductDetialComHeight = window.innerHeight * 1.5 + 'px';

	AbortComHeight.value = window.innerHeight * 1.3 + 'px';

	ProductComData.value = {
		productComHeight,
		productComTop
	};

	RightInfoComData.value = {
		infoWidth,
		infoHeight
	};

	infoHeight= window.innerHeight * 0.65 + 'px';
	let top = -(window.innerHeight * 0.65 / 2) + parseInt(productComTop.split('px')[0]) + 'px';
	productComTop = top;
	LeftInfoComData.value = {
		infoWidth,
		infoHeight,
		productComTop
	};

	top = -parseInt(infoHeight.split('px')[0]) / 2 + parseInt(productComTop.split('px')[0]) + 'px';
	productComTop = top;
	CooperateComData.value = {
		CooperateComHeight,
		productComTop
	};

	PoductDetialComData.value = {
		PoductDetialComHeight,
		productComTop
	};
}
</script>

<style lang="scss" scoped>
.home{
	position: absolute;
    width: 100%;
    height: 100%;
    top: 0px;
    left: 0px;
}
</style>
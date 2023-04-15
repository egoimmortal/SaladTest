<template>
	<div class="home">
		<VideoCom :src="videoSrc"></VideoCom>
		<AbortCom></AbortCom>
		<RightInfoCom :props="RightInfoComData"></RightInfoCom>
	</div>
</template>

<script lang="ts" setup>
import VideoCom from '@/components/VideoCom.vue';
import AbortCom from '@/components/AbortCom.vue';
import RightInfoCom from '@/components/info/RightInfoCom.vue';

import { onMounted, ref } from 'vue';

const videoSrc = ref('https://www.youtube.com/embed/8_4JRK4QkqU?autohide=0&branding=0&controls=0&showinfo=0&autoplay=1&mute=1&rel=0&enablejsapi=1&widgetid=1');
const RightInfoComData = ref<{width: string, height: string}>({width: '0px',height: '0px'});

onMounted(() => {
	Resize();

    window.addEventListener('resize', Resize);
});

function Resize(){
	let width = window.innerWidth * 0.93 + 'px';
	let height = window.innerHeight * 0.4 + 'px';
	console.log('width = ', width);
	RightInfoComData.value = {
		width,
		height
	}
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
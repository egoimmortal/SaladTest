<template>
	<NavCom @OpenFullInfo="OpenFullInfo" @CloseFullInfo="CloseFullInfo"></NavCom>
	<router-view/>
	<InfoFullCom :show="fullInfoPageShow"></InfoFullCom>
</template>

<script lang="ts" setup>
import NavCom from '@/components/NavCom.vue';
import InfoFullCom from './components/info/InfoFullCom.vue';
import { ref } from 'vue';

const fullInfoPageShow = ref(false);

const OpenFullInfo = () => {
	console.log('app OpenFullInfo');
	fullInfoPageShow.value = true;
};

const CloseFullInfo = () => {
	console.log('app CloseFullInfo');
	fullInfoPageShow.value = false;
};
</script>

<style lang="scss">
:root{
	--window-scale: 1;
	--window-page: 1;
	--window-info: 2;
	--window-video: 3;
	--window-full-info-page: 4;
	--window-navbar: 5;
}

#app {
	// font-family: Avenir, Helvetica, Arial, sans-serif;
	// -webkit-font-smoothing: antialiased;
	// -moz-osx-font-smoothing: grayscale;
	font-family: "Proxima Nova Bold";
	text-align: center;
	color: #2c3e50;
}

nav {
	padding: 30px;

	a{
		font-weight: bold;
		color: #2c3e50;

		&.router-link-exact-active{
			color: #42b983;
		}
	}
}

html{
	font-family: "Proxima Nova Bold";
}

body{
	background-color: #E5E5E5 !important;
}

.pink-dot:after{
	font-size: 50px;
	color: #ee6c8a;
	content: ".";
	position: absolute;
	right: -10%;
	bottom: -6px;
}

.wave{
    color: #26C6D0;
    border: 3px solid #26C6D0;
    width: 180px;
    height: 5px;
    background: #26C6D0;
}
</style>

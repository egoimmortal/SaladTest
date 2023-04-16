<template>
    <nav class="navbar" :class="{'block': !navTop}">
		<div class="container-fluid">
			<div class="left-side" :class="{'open': !fullInfo, 'close': fullInfo}"></div>
			<div class="right-side">
				<div class="info" :class="{'open': !fullInfo, 'close': fullInfo}">
					<span>
						START YOUR PROJECT
					</span>
				</div>
				<div class="menu" :class="{'open': !fullInfo, 'close': fullInfo}" @click="openFullInfo">
					<div></div>
					<div></div>
					<div></div>
				</div>
				<div class="closeFullInfo" :class="{'open': fullInfo, 'close': !fullInfo}" @click="closeFullInfo"></div>
			</div>
		</div>
    </nav>
</template>

<script lang="ts" setup>
import { onMounted, onUnmounted, ref, watch, defineEmits } from 'vue';

const navTop = ref(true);
const fullInfo = ref(false);
const emit = defineEmits(['OpenFullInfo', 'CloseFullInfo']);

onMounted(() => {
	window.addEventListener('scroll', OnScroll);
})

watch(() => window.pageYOffset, () => {
	console.log(1);
})

onUnmounted(() => {
	window.removeEventListener('scroll', OnScroll);
})

function OnScroll(){
	if(window.pageYOffset < 100)
		navTop.value = true;
	else
		navTop.value = false;
}

function openFullInfo(){
	fullInfo.value = true;
    emit('OpenFullInfo');
}

const closeFullInfo = () => {
	fullInfo.value = false;
    emit('CloseFullInfo');
}
</script>

<style lang="scss" scoped>
nav {
	position: fixed;
	width: 100%;
	height: 100px;
	display: flex;
    justify-content: flex-end;
	padding: 1%;
    background-color: rgba(255, 255, 255, 0);
    z-index: var(--window-navbar);

	&.block{
		background-color: #FFFFFF;
	}

	& *:first-child{
		height: 100%;
	}

	.left-side{
		position: relative;
		left: 5%;
		height: 90%;

		&.open{
			content: url('@/assets/logo2.png');
		}

		&.close{
			content: url('@/assets/logo3.png');
		}
	}

	.right-side{
		display: flex;
		flex-direction: row;
		align-items: center;
		position: relative;
		right: 5%;
		height: 50%;
		cursor: pointer;

		div{
			font-weight: bold;
			color: #FFFFFF;
			background: linear-gradient(90deg, #4EE5EA 3.94%, #26D0A8 94.73%);
			border-radius: 24px;

			span {
				display: inline-block;
				width: 80%;
				white-space: nowrap;
			}
		}

		& > div:not(:last-child){
			margin-right: 40px;
		}

		.info{
			display: flex;
			justify-content: space-between;

			*{
				display: flex;
				align-items: center;
			}
		}

		.menu{
			display: flex;
			flex-direction: column;
			justify-content: space-between;
			align-items: flex-end;
			background: #FFFFFF00 !important;

			*{
				color:#414042 !important;
				border: solid;
				margin-top: 3px;
				width: 30px;
				border: 0.5px solid #414042;
			}

			*:last-child{
				width: 26px;
			}
		}

		.closeFullInfo{
			&:before{
				content: '';
				height: 30px;
				border-left: 2px solid #fff;
				position: absolute;
				transform: rotate(-45deg);
				left: 28px;
			}
			&:after{
				content: '';
				height: 30px;
				border-left: 2px solid #fff;
				position: absolute;
				transform: rotate(45deg);
				left: 28px;
			}
		}

		.open{
			display: flex;
		}

		.close{
			display: none;
		}
	}
}
</style>
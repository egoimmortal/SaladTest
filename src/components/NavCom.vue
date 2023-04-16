<template>
    <nav class="navbar" :class="{'block': !navTop}">
		<div class="container-fluid">
			<div class="left-side">
				<img src="@/assets/logo2.png" />
			</div>
			<div class="right-side">
				<div class="info">
					<span>
						START YOUR PROJECT
					</span>
				</div>
				<div class="menu">
					<div></div>
					<div></div>
					<div></div>
				</div>
			</div>
		</div>
    </nav>
</template>

<script lang="ts" setup>
import { onMounted, onUnmounted, ref, watch } from 'vue';

const navTop = ref(true);
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
			background: #FFFFFF !important;

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
	}
}
</style>
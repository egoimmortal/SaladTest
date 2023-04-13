<template>
    <div>
        <iframe ref="video" :src="props.src"
            title="DigiSalad Website Video-v3"
            frameborder="0"
            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
            allowfullscreen>
        </iframe>
    </div>
</template>

<script lang="ts" setup>
import { defineProps, ref } from 'vue';
const props = defineProps<{
    src: string
}>();
</script>

<style lang="scss">
.ytp-chrome-top{
    display: none !important;
}

.html5-video-container,
.html5-main-video{
    width: 100% !important;
    height: 100% !important;
}
</style>

<style lang="scss" scoped>
div{
    position: relative;
    height: 100%;
    width: 100%;
}

iframe{
    position: absolute;
    top: 0px;
    left: 0px;
    width: 100%;
    height: 100%;
    z-index: var(--window-video);

    *{
        width: 100% !important;
        height: 100% !important;
    }
}
</style>
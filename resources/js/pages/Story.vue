<template>
    <div class="flex h-screen items-center justify-center bg-white">
        <Vue3Lottie
            ref="scrollAnim"
            :animationData="scrollAnimation"
            :loop="false"
            :autoplay="false"
            :style="{ width: '500px', height: '500px' }"
        />
    </div>
</template>

<script setup>
import scrollAnimation from '@/Assets/lottie/scroll-progress.json';
import { onMounted, onUnmounted, ref } from 'vue';

const scrollAnim = ref(null);
let animInstance;

onMounted(() => {
    animInstance = scrollAnim.value.getLottie();
    window.addEventListener('scroll', handleScroll);
});

onUnmounted(() => {
    window.removeEventListener('scroll', handleScroll);
});

function handleScroll() {
    const scrollTop = document.documentElement.scrollTop;
    const docHeight =
        document.documentElement.scrollHeight - window.innerHeight;
    const scrollPercent = scrollTop / docHeight;
    const frame = animInstance.totalFrames * scrollPercent;
    animInstance.goToAndStop(frame, true);
}
</script>

<template>
    <div
        class="rounded-xl bg-gray-800 p-6 shadow-lg transition hover:bg-gray-700"
        @mouseenter="playAnimation"
        @mouseleave="stopAnimation"
    >
        <Vue3Lottie
            ref="cardAnim"
            :animationData="cardAnimation"
            :loop="false"
            :autoplay="false"
            :style="{ width: '150px', height: '150px' }"
        />
        <h2 class="mt-4 text-white">{{ title }}</h2>
    </div>
</template>

<script setup>
import cardAnimation from '@/Assets/lottie/hover-icon.json';
import { ref } from 'vue';

const props = defineProps({
    title: String,
});

const cardAnim = ref(null);

function playAnimation() {
    cardAnim.value.getLottie().play();
}
function stopAnimation() {
    cardAnim.value.getLottie().stop();
}
</script>

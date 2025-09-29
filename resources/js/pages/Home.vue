<template>
    <div
        class="flex min-h-screen flex-col items-center justify-center bg-gray-900 text-white"
    >
        <Vue3Lottie
            :animationData="heroAnimation"
            :loop="true"
            :autoplay="true"
            :style="{ width: '400px', height: '400px' }"
        />
        <h1 class="mt-6 text-4xl font-bold">Hi, I’m Samiul Islam</h1>
        <p class="mt-2 text-lg opacity-80">
            Full-Stack Developer | Laravel & Vue.js
        </p>
    </div>
</template>

<script setup>
import heroAnimation from '@/Assets/lottie/coding.json';
</script>

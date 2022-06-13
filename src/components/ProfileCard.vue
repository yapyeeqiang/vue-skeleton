<script setup lang="ts">
import { onMounted, ref } from 'vue'

interface User {
    name: string
    pic: string
    bio: string
}

const loadUserData = async (): Promise<User> => {
    return new Promise((resolve) => {
        setTimeout(() => {
            resolve({
                name: 'Yap Yee Qiang',
                pic: 'https://yeeqiang.me/avatar.jpeg',
                bio: 'A tech enthusiast and an educator believes that everyone can be a self-taught developer.',
            })
        }, 2000)
    })
}

const userData = ref(await loadUserData())
</script>

<template>
    <div class="flex items-start space-x-4 bg-white p-8 max-w-2xl mx-auto rounded-xl w-full">
        <div class="h-24 w-24 object-contain flex-shrink-0">
            <img class="h-full w-full rounded-full border-[5px] border-[#42b883] p-1" :src="userData?.pic" />
        </div>

        <div class="space-y-2 flex-1">
            <span class="uppercase text-[#777] text-sm"> Written By </span>
            <h3 class="text-[#222] text-2xl">{{ userData?.name }}</h3>
            <p class="text-[#777]">{{ userData?.bio }}</p>
        </div>
    </div>
</template>

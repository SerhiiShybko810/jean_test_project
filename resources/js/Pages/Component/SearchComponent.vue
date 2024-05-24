<script setup>
const props = defineProps({
    avatar: String,
    banner: String,
    text: String,
    fontWeight: String,
    fontFamily: String,
    fontSize: String,
    placeColor: String,
})

import Input from './InputComponent.vue'
import { CameraIcon } from '@heroicons/vue/16/solid';
import { LinkIcon } from '@heroicons/vue/16/solid';
</script>

<template>
    <div class="w-full rounded-xl bg-white p-4 shadow-md flex items-center space-x-6">
        <div class="relative  w-[55px] h-[49px]">
            <img :src="avatar" class="rounded-full w-full h-full object-cover" />
            <img :src="banner" class="absolute -bottom-1 -right-1 border-2 border-white rounded-full" />
        </div>
        <div class="w-full relative">
            <Input :placeholder="text" :fontWeight="fontWeight" :fontFamily="fontFamily" :fontSize="fontSize"
                :placeColor="placeColor" />

            <CameraIcon class="absolute right-16 top-1/3 w-5 h-5 sm:block hidden" />
            <LinkIcon class="absolute right-6 top-1/3 w-5 h-5 sm:block hidden" />
        </div>
    </div>
</template>
<script setup>
import { EllipsisHorizontalIcon, HeartIcon, BookmarkIcon, ChatBubbleOvalLeftEllipsisIcon } from '@heroicons/vue/16/solid'
import { ArrowUpTrayIcon } from '@heroicons/vue/20/solid'
const props = defineProps({
    avatar2: String,
    avatar3: String,
    avatar4: String,
    avatar5: String,
    avatar6: String,
    banner: String,
    title: String,
    name: String,
    time: String,
    btnText: String,
    video: String,
    text: String,
    commentTime: String,
    heart: String,
    message: String,
    bookMark: String,
    open: Boolean,
    handleModal: Function,
})
</script>

<template>
    <div class="bg-white/60 rounded-lg shadow-md px-4 py-6">
        <div class="flex justify-between items-center">
            <div class="flex items-center">
                <div class="relative  w-[49px] h-[49px]">
                    <img :src="avatar2" class="rounded-full w-full h-full object-cover" />
                    <img :src="banner" class="absolute -bottom-1 -right-1 border-2 border-white rounded-full" />
                </div>
                <div class="font-manr pl-4 pr-2">
                    <span class="font-bold text-sm text-gray-900">{{ name }}</span>
                    <p class="font-semibold text-[10px] text-gray-600">{{ time }}</p>
                </div>
                <button
                    class="rounded-full bg-[#175265]/5 items-end flex px-2 py-1 text-gray-900 font-manr font-bold text-[10px] mt-6">{{
                        btnText
                    }}</button>
            </div>
            <div class="bg-[#175265]/5 text-gray-900 p-1 rounded-full w-6 h-6 cursor-pointer">
                <EllipsisHorizontalIcon />
            </div>
        </div>
        <div class="py-6 flex lg:flex-row flex-col lg:space-x-2 lg:spacee-y-0 space-x-0 space-y-4">
            <div :class="'' + (video ? 'lg:w-3/5' : 'lg:w-full')">
                <span class=" font-manr font-bold text-sm text-black">{{ title }}</span>
                <p class=" font-manr text-gray-700 font-medium py-1">{{ text }}</p>
            </div>
            <div :class="'' + (video ? 'lg:w-2/5' : 'w-0')">
                <video autoPlay loop controls playsinline autoPictureInPicture
                    :class="'rounded-xl drop-shadow-2 ' + ' ' + (video ? 'block' : 'hidden')">
                    <source :src="video" type="video/mp4" />
                    Your browser does not support the video tag.
                </video>
            </div>
        </div>
        <div class="flex justify-between items-center">
            <div class="flex lg:flex-row flex-col justifiy-between lg:space-x-3 space-x-0 lg:space-y-0 space-y-2">
                <div class="flex justify-between space-x-2 items-center">
                    <div class="flex space-x-1 items-center">
                        <div class="rounded-full p-2 bg-[#175265]/5 w-8 h-8 hover:scale-125">
                            <HeartIcon />
                        </div>
                        <p class="font-bold font-manr text-gray-800 text-xs">{{ heart }}</p>
                    </div>
                    <div class="flex space-x-1 items-center">
                        <div class="rounded-full p-2 bg-[#175265]/5 w-8 h-8 hover:scale-125">
                            <ChatBubbleOvalLeftEllipsisIcon />
                        </div>
                        <p class="font-bold font-manr text-gray-800 text-xs">{{ message }}</p>
                    </div>
                    <div class="flex space-x-1 items-center">
                        <div class="rounded-full p-2 bg-[#175265]/5 w-8 h-8 hover:scale-125">
                            <BookmarkIcon />
                        </div>
                        <p class="font-bold font-manr text-gray-800 text-xs">{{ bookMark }}</p>
                    </div>
                </div>
                <div class="flex items-center">
                    <div class="w-6 h-6 opacity-40 z-0">
                        <img :src="avatar6"
                            class="rounded-full object-cover w-full h-full border-2 border-solid border-white" />
                    </div>
                    <div class="w-6 h-6 opacity-60 -ml-2.5 z-1">
                        <img :src="avatar5"
                            class="rounded-full object-cover w-full h-full border-2 border-solid border-white" />
                    </div>
                    <div class="w-6 h-6 opacity-70 -ml-2.5 z-2">
                        <img :src="avatar4"
                            class="rounded-full object-cover w-full h-full border-2 border-solid border-white" />
                    </div>
                    <div class="w-6 h-6 -ml-2.5 z-10">
                        <img :src="avatar3"
                            class="rounded-full object-cover w-full h-full border-2 border-solid border-white" />
                    </div>
                </div>
                <div class="font-manr text-gray-600 text-[10px] font-semibold flex items-center">
                    <p>{{ commentTime }}</p>
                </div>
            </div>
            <button
                class="rounded-lg text-gray-900 text-xs font-extrabold flex p-2 items-center space-x-2 justify-between bg-[#175265]/5"
                @click="handleModal">
                <ArrowUpTrayIcon class="w-4 h-4" />
                <span>Share</span>
            </button>
        </div>
    </div>
</template>
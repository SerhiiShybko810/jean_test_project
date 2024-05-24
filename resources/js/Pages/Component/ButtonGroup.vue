<script setup>
import { ref } from 'vue'
import SingleButton from './SingleButton.vue'

const tabButtons = [
    { text: 'All' },
    { text: '🤘  Meetups' },
    { text: '❤️ Aide' },
    { text: '🏠  Immobilier' },
    { text: '💰 Action ETF' },
    { text: '🔮 Cryptos' },
]
const setTab = ref(0)

const handleSetTab = (val) => {
    setTab.value = val
}
</script>

<template>
    <div class="">
        <div class="md:flex hidden justify-center items-center md:space-x-2 space-x-0 md:space-y-0 space-y-2">
            <SingleButton v-for="(item, index) in tabButtons" :key="index" @click="handleSetTab(index)"
                :text="item.text" borderRadius="rounded-full" fontFamily="font-manr" fontColor="text-gray-700"
                fontSize="text-xs" fontWeight="font-bold" bgColor="bg-[#175265]/5" paddingX="px-4" paddingY="py-3"
                :index="index" :setTab="setTab" />
        </div>
        <select class="md:hidden block px-2 py-1 rounded-md bg-[#175265]/5">
            <option v-for="(item, index) in tabButtons" :key="index" @click="handleSetTab(index)"
                class="text-gray-700 font-bold text-md font-manr">
                {{ item.text }}
            </option>
        </select>
    </div>
</template>
<script setup>
const props = defineProps({
    text: String,
    borderRadius: String,
    fontFamily: String,
    fontSize: String,
    fontColor: String,
    bgColor: String,
    fontWeight: String,
    paddingX: String,
    paddingY: String,
    index: String,
    setTab: String,
    Icon: String,
})
</script>
<template>
    <button
        :class="' flex items-center ' + fontFamily + ' ' + fontSize + ' ' + fontWeight + ' ' + paddingX + ' ' + paddingY + ' ' + borderRadius + ' ' + (setTab === index ? ' bg-gradient-to-b from-[#272A31] to-[#17131F] text-white' : fontColor + ' ' + bgColor) + ' ' + (Icon ? 'space-x-2' : '')">
        <img :src="Icon" />
        <span>
            {{ text }}
        </span>
    </button>
</template>
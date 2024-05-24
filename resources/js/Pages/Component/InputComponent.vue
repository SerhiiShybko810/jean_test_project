<script setup>
const props = defineProps({
    placeholder: String,
    width: String,
    fontWeight: String,
    fontFamily: String,
    fontSize: String,
    placeColor: String,
})
</script>
<template>
    <input :placeholder="placeholder"
        :class="' w-full p-4 bg-[#175265]/5 rounded-lg outline-none ' + fontWeight + ' ' + fontFamily + ' ' + fontSize + ' ' + placeColor" />
</template>
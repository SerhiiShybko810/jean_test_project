<script setup>
import { Dialog, DialogPanel, TransitionChild, TransitionRoot } from '@headlessui/vue'
import { XMarkIcon } from '@heroicons/vue/16/solid';
import Input from './InputComponent.vue'

const tabButtons = [
    { text: '🤘  Meetups' },
    { text: '❤️ Aide' },
    { text: '🏠  Immobilier' },
    { text: '💰 Action ETF' },
    { text: '🔮 Cryptos' },
]
const props = defineProps({
    open: Boolean,
    handleModal: Function,
    avatar: String,
    text: String,
    banner: String,
})
</script>
<template>
    <TransitionRoot as="template" :show="open">
        <Dialog class="relative z-20" @close="open = false">
            <TransitionChild as="template" enter="ease-out duration-300" enter-from="opacity-0" enter-to="opacity-100"
                leave="ease-in duration-200" leave-from="opacity-100" leave-to="opacity-0">
                <div class="fixed inset-0 bg-gray-500 bg-opacity-80 transition-opacity" />
            </TransitionChild>

            <div class="fixed inset-0 z-10 w-screen overflow-y-auto">
                <div class="flex min-h-full items-end justify-center p-4 text-center sm:items-center sm:p-0">
                    <TransitionChild as="template" enter="ease-out duration-300"
                        enter-from="opacity-0 translate-y-4 sm:translate-y-0 sm:scale-95"
                        enter-to="opacity-100 translate-y-0 sm:scale-100" leave="ease-in duration-200"
                        leave-from="opacity-100 translate-y-0 sm:scale-100"
                        leave-to="opacity-0 translate-y-4 sm:translate-y-0 sm:scale-95">
                        <DialogPanel
                            class="relative transform overflow-hidden rounded-xl bg-white text-left shadow-xl transition-all sm:my-8 sm:w-full sm:max-w-lg">
                            <div class="bg-white p-4">
                                <div class="sm:flex sm:items-center sm:justify-between pb-2">
                                    <div class="text-center items-center flex space-x-2">
                                        <p class=" font-manr font-bold text-base text-gray-600">Posting in</p>
                                        <div class="relative">
                                            <select
                                                class="py-1.5 px-1 rounded-full w-32 bg-[#175265]/10 outline-none block appearance-none leading-tight">
                                                <option v-for="(item, index) in tabButtons" :key="index"
                                                    @click="handleSetTab(index)"
                                                    class="text-gray-900 font-bold text-md font-manr">
                                                    {{ item.text }}
                                                </option>
                                            </select>
                                            <div
                                                class="pointer-events-none absolute inset-y-0 right-0 flex items-center px-2 text-gray-700">
                                                <svg class="fill-current h-4 w-4" xmlns="http://www.w3.org/2000/svg"
                                                    viewBox="0 0 20 20">
                                                    <path
                                                        d="M9.293 12.95l.707.707L15.657 8l-1.414-1.414L10 10.828 5.757 6.586 4.343 8z" />
                                                </svg>
                                            </div>
                                        </div>
                                    </div>
                                    <div class="bg-[#175265]/5 w-8 h-8 rounded-full p-1.5 cursor-pointer"
                                        @click="handleModal">
                                        <XMarkIcon />
                                    </div>
                                </div>
                                <div class="w-full flex space-x-4 py-4">
                                    <div class="relative  w-[55px] h-[49px]">
                                        <img :src="avatar" class="rounded-full w-full h-full object-cover" />
                                        <img :src="banner"
                                            class="absolute -bottom-1 -right-1 border-2 border-white rounded-full" />
                                    </div>
                                    <div class="w-full relative">
                                        <Input :placeholder="text" :fontWeight="fontWeight" :fontFamily="fontFamily"
                                            :fontSize="fontSize" :placeColor="placeColor" />
                                    </div>
                                </div>
                                <textarea class="w-full h-60 bg-[#175265]/5 rounded-lg p-2 resize-none outline-none"
                                    placeholder="Write Something" />
                                <div class="pt-4 flex justify-end">
                                    <button
                                        class="flex justify-center rounded-lg bg-gradient-to-b from-[#272A31] to-[#17131F]/90"
                                        @click="handleModal">
                                        <p
                                            class="text-white font-extrabold text-sm p-3 border-r-2 border-[#FAFAFF]/20 h-full">
                                            Publish</p>
                                        <div class="p-3 w-full text-white">
                                            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"
                                                fill="currentColor" class="w-6 h-6">
                                                <path fill-rule="evenodd"
                                                    d="M12 2.25c-5.385 0-9.75 4.365-9.75 9.75s4.365 9.75 9.75 9.75 9.75-4.365 9.75-9.75S17.385 2.25 12 2.25ZM12.75 6a.75.75 0 0 0-1.5 0v6c0 .414.336.75.75.75h4.5a.75.75 0 0 0 0-1.5h-3.75V6Z"
                                                    clip-rule="evenodd" />
                                            </svg>
                                        </div>
                                    </button>
                                </div>
                            </div>
                        </DialogPanel>
                    </TransitionChild>
                </div>
            </div>
        </Dialog>
    </TransitionRoot>
</template>

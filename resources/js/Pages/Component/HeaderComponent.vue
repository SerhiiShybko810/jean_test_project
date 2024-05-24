<script setup>
import { ref } from 'vue'
import { Dialog, DialogPanel } from '@headlessui/vue'
import { Bars3Icon, XMarkIcon } from '@heroicons/vue/24/outline'
import { Link } from '@inertiajs/vue3'

import logoImg from '../../../assets/image/header/logo.png'
import starImg from '../../../assets/image/header/star.png'
const navigation = [
    { name: 'Feed', href: '#' },
    { name: 'Space', href: '#' },
    { name: 'Rewards', href: '#' },
]
const activeTab = ref(0)

const handleTab = (val) => {
    activeTab.value = val
}

const mobileMenuOpen = ref(false)
</script>

<template>
    <header class="inset-x-10 top-0 z-50">
        <nav class="flex items-center justify-between p-6 lg:px-8" aria-label="Global">
            <div class="flex">
                <a href="#" class="flex items-center space-x-4 p-1.5">
                    <img class="h-auto w-auto" :src="logoImg" alt="" />
                    <span class="text-grey-900 font-bold text-lg font-manr">Finnary</span>
                </a>
            </div>
            <div class="hidden lg:flex lg:gap-x-1 bg-black/10 p-1 rounded-xl w-[447px]">
                <button v-for="(item, index) in navigation" :key="index" @click="handleTab(index)"
                    :class="'text-sm font-bold leading-6 py-1 rounded-lg flex-1 ' + (activeTab === index ? 'bg-white text-gray-900' : 'transparent text-gray-600')">
                    {{ item.name }}
                </button>
            </div>
            <div
                class="hidden lg:flex lg:justify-between lg:items-center border border-gray/5 rounded-xl w-[106px] px-2 py-1">
                <span><img :src="starImg" /></span>
                <button href="#"
                    class=" text-xs bg-[#175265]/5 w-[57px] rounded-md py-1 px-1 font-extrabold leading-6 text-gray-900 font-manr">Log
                    in</button>
            </div>
            <div class="flex lg:hidden">
                <button type="button"
                    class="-m-2.5 inline-flex items-center justify-center rounded-md p-2.5 text-gray-700"
                    @click="mobileMenuOpen = true">
                    <span class="sr-only">Open main menu</span>
                    <Bars3Icon class="h-6 w-6" aria-hidden="true" />
                </button>
            </div>
        </nav>
        <Dialog class="lg:hidden" @close="mobileMenuOpen = false" :open="mobileMenuOpen">
            <div class="fixed inset-0 z-50" />
            <DialogPanel
                class="fixed inset-y-0 right-0 z-50 w-full overflow-y-auto bg-white px-6 py-6 sm:max-w-sm sm:ring-1 sm:ring-gray-900/10">
                <div class="flex items-center justify-between">
                    <Link href="#" class="flex items-center space-x-4 p-1.5">
                    <img class="h-auto w-auto" :src="logoImg" alt="" />
                    <span class="text-grey-900 font-bold text-lg font-manr">Finnary</span>
                    </Link>
                    <button type="button" class="-m-2.5 rounded-md p-2.5 text-gray-700" @click="mobileMenuOpen = false">
                        <span class="sr-only">Close menu</span>
                        <XMarkIcon class="h-6 w-6" aria-hidden="true" />
                    </button>
                </div>
                <div class="mt-6 flow-root">
                    <div class="-my-6 divide-y divide-gray-500/10">
                        <div class="space-y-2 py-6">
                            <a v-for="item in navigation" :key="item.name" :href="item.href"
                                class="-mx-3 block rounded-lg px-3 py-2 text-base font-semibold leading-7 text-gray-900 hover:bg-gray-50">{{
                                    item.name }}</a>
                        </div>
                        <div class="py-6">
                            <a href="#"
                                class="-mx-3 block rounded-lg px-3 py-2.5 text-base font-semibold leading-7 text-gray-900 hover:bg-gray-50">Log
                                in</a>
                        </div>
                    </div>
                </div>
            </DialogPanel>
        </Dialog>
    </header>
</template>
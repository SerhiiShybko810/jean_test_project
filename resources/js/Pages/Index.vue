<script setup>
import { ref } from 'vue'
import HeaderComponent from '@/Pages/Component/HeaderComponent.vue'
import SearchBox from '@/Pages/Component/SearchComponent.vue'
import ButtonGroup from '@/Pages/Component/ButtonGroup.vue'
import SingleButton from '@/Pages/Component/SingleButton.vue'
import Card from '@/Pages/Component/CardComponent.vue'
import ModalComponent from '@/Pages/Component/ModalComponent.vue'
import user1 from '../../assets/image/user/user1.png'
import user2 from '../../assets/image/user/user2.png'
import user3 from '../../assets/image/user/user3.png'
import user4 from '../../assets/image/user/user4.png'
import user5 from '../../assets/image/user/user5.png'
import user6 from '../../assets/image/user/user6.png'
import banner from '../../assets/image/banner.png'
import BarImg from '../../assets/image/barIcon.png'
import Video from '../../assets/image/section.mp4'
const cardData = [
    {
        name: 'Bradley Lawlor',
        time: 'Posted 13 min ago in',
        title: 'Mon kit de démarrage pour investisseurs débutants',
        text: 'Je rencontre des investisseurs qui souhaitent se lancer quasiment tous les jours. La question qui revient tout le temps est : je commence par quoi ? Le profil est souvent le même : entre 25 et 35 ans, cadre avec un bon salaire.Ma réponse: Installer l’app Finary Mettre en place un matelas de sécurité de 3 à 6 mois de dépenses...',
        avatar2: user2,
        avatar3: user3,
        avatar4: user4,
        avatar5: user5,
        avatar6: user6,
        banner: banner,
        btnText: '🤘 Meetups',
        commentTime: 'Julia a repondu en commentaire  il y a 4 min',
        heart: "34",
        message: "122",
        bookMark: "2",
    },
    {
        name: 'Bradley Lawlor',
        time: 'Posted 13 min ago in',
        title: 'Mon kit de démarrage pour investisseurs débutants',
        text: 'Je rencontre des investisseurs qui souhaitent se lancer quasiment tous les jours. La question qui revient tout le temps est : je commence par quoi ? Le profil est souvent le même : entre 25 et 35 ans, cadre avec un bon salaire.Ma réponse: Installer l’app Finary Mettre en place un matelas de sécurité de 3 à 6 mois de dépenses...',
        avatar2: user2,
        avatar3: user3,
        avatar4: user4,
        avatar5: user5,
        avatar6: user6,
        btnText: '🤘 Meetups',
        commentTime: 'Julia a repondu en commentaire  il y a 4 min',
        video: Video,
        heart: "34",
        message: "122",
        bookMark: "2",
    }
]

const handleModal = () => {
    modalOpen.value = !modalOpen.value
}

const modalOpen = ref(false)
</script>

<template>
    <div class="bg-orange-50/50 min-h-screen pb-56">
        <div>
            <HeaderComponent />
            <div class="mx-auto container max-w-[768px] px-6">
                <SearchBox :avatar="user1" :banner="banner" text="Lancez une discussion sur un sujet"
                    fontWeight="font-bold" fontFamily="font-manr" fontSize="text-sm" placeColor="text-gray-700" />
                <div class="flex justify-between items-center py-10">
                    <ButtonGroup />
                    <SingleButton text="filter" borderRadius="rounded-xl" fontFamily="font-manr"
                        fontColor="text-gray-700" fontSize="text-xs" fontWeight="font-bold" paddingX="px-4"
                        paddingY="py-3" :Icon="BarImg" />
                </div>
                <div class="flex flex-col space-y-3">
                    <Card v-for="(item, index) in cardData" :key="index" :avatar2="item.avatar2" :avatar3="item.avatar3"
                        :avatar4="item.avatar4" :avatar5="item.avatar5" :avatar6="item.avatar6" :banner="item.banner"
                        :btnText="item.btnText" :name="item.name" :time="item.time" :title="item.title"
                        :text="item.text" :commentTime="item.commentTime" :video="item.video" :heart="item.heart"
                        :message="item.message" :bookMark="item.bookMark" :handleModal="handleModal" />
                </div>

                <ModalComponent :open="modalOpen" :handleModal="handleModal" :avatar="user1" :banner="banner"
                    text="Title of your post" fontWeight="font-bold" fontFamily="font-manr" fontSize="text-sm"
                    placeColor="text-gray-400" />
            </div>
        </div>
    </div>
</template>
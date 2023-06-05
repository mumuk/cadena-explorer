<template>
  <div class="modal-overlay fixed bg-[#0d0d0d] bg-opacity-95 inset-0  overflow-hidden">

    <GenericBtn @click="$emit('closeModal')" class="absolute w-14 h-14">
      <CloseIcon/>
    </GenericBtn>

    <div class="content absolute opacity-100 w-[678px] h-[672px]">
      <div class="flex flex-wrap justify-between items-center h-full ">

        <GenericBtn class="m-auto w-14 h-14" @click="scrollLeft" :disabled="disableScrollLeft">
          <LeftIcon/>
        </GenericBtn>

        <div class="flex-col ">

          <p class="modal-header flex justify-between text-white text-3xl leading-7">
            <span>{{ headerText }}</span>
            <span>#{{ activeCard.id }}</span>
          </p>

          <div class="modal-sub-header flex text-white underline my-5">

            <div class="flex items-center ">
              <OwnerIcon/>
              <NuxtLink class="ml-2 mr-5 " to="#">Owner</NuxtLink>
            </div>

            <div class="flex items-center ">
              <CollectionIcon/>
              <NuxtLink class="ml-2 mr-5 " to="#">Collection</NuxtLink>
            </div>

            <div class="flex items-center ">
              <ShareIcon/>
              <NuxtLink class="ml-2 mr-5 cursor-pointer" @click="copyToClipboard()" to="#">Share</NuxtLink>
            </div>

          </div>

          <div class="carousel h-1/2 opacity-100 mb-4">
            <img :src="activeCard.imageUrl" alt="" class="h-full rounded-2xl w-[512px] ">
          </div>

          <GenericBtn class="m-auto w-56 h-14 text-sm">OPEN MARKETPLACE</GenericBtn>
        </div>

        <GenericBtn class="m-auto w-14 h-14" @click="scrollRight" :disabled="disableScrollRight">
          <RightIcon/>
        </GenericBtn>


      </div>

    </div>

  </div>


</template>

<script setup>
import {computed} from "vue";
import GenericBtn from "../ui/GenericBtn";
import CloseIcon from "./icons/CloseIcon";
import LeftIcon from "./icons/LeftIcon";
import RightIcon from "./icons/RightIcon";
import OwnerIcon from "./icons/OwnerIcon";
import CollectionIcon from "./icons/CollectionIcon";
import ShareIcon from "./icons/ShareIcon";


defineEmits(['closeModal'])
const {cardList, activePropsIndex, headerText} = defineProps(['cardList', 'activePropsIndex', 'headerText'])

const route = useRoute()
const path = computed(() => window.location.origin + route.path)


let selectedIndex = ref(activePropsIndex)
const activeCard = computed(() => cardList[selectedIndex.value])

const copyToClipboard = () => {
  navigator.clipboard.writeText(path.value)
  alert('URL copied to Clipboard')
}

const disableScrollRight = computed(() => selectedIndex.value === cardList.length - 1)
const disableScrollLeft = computed(() => selectedIndex.value === 0)


const scrollRight = () => selectedIndex.value++
const scrollLeft = () => selectedIndex.value--


</script>

<style scoped>

.content {
  left: calc(50% - 672px / 2 + 22px);
  top: calc(50% - 678px / 2 + 22px);
}

</style>
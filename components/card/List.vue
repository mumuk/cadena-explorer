<template>
  <div>
    <Teleport to="body">

      <ModalDialog v-if="isShowModal"
                   :activePropsIndex="activePhotoIndex"
                   :cardList="cardList"
                   :headerText="headerText"
                   @closeModal="closeModal"
      />
    </Teleport>
    <div>
      <CardListHeader/>
    </div>
    <div class=" title text-sm pb-6 mb-8 border-b-2  border-b-[#353945]">
      <span>NFTs</span>
    </div>

    <div class="grid grid-cols-6 gap-5 top-0 max-w-[1200px]">

      <CardItem v-for="(item, index) in cardList"
                :key="item.id"
                :text="headerText"
                :imageUrl="item.imageUrl"
                :infoUrl="item.infoUrl"
                :id="item.id"
                @click="showModal(index)"
      />
    </div>
  </div>
</template>

<script setup>
const {cardList} = defineProps(['cardList'])
const headerText = "Kor Blockchain OG Badge"
const isShowModal = ref(false)
const activePhotoIndex = ref(null)

const showModal = (index) => {
  activePhotoIndex.value = index
  isShowModal.value = true
  document.body.style.overflow = 'hidden'
}

const closeModal = () => {
  isShowModal.value = false
  document.body.style.overflow = 'false'
}
</script>

<style scoped>
/*.title {*/
/*  border-bottom: 1px solid grey;*/
/*}*/
</style>
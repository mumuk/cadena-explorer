<template>
  <div class="h-[100px] flex justify-between z-20 mb-12">
    <div class="flex  items-center">
      <GenericBtn class=" w-14 h-14">
        <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path fill-rule="evenodd" clip-rule="evenodd"
                d="M14.7075 15.8814L10.8275 12.0014L14.7075 8.12145C15.0975 7.73145 15.0975 7.10145 14.7075 6.71145C14.3175 6.32145 13.6875 6.32145 13.2975 6.71145L8.7075 11.3014C8.3175 11.6914 8.3175 12.3214 8.7075 12.7114L13.2975 17.3014C13.6875 17.6914 14.3175 17.6914 14.7075 17.3014C15.0875 16.9114 15.0975 16.2714 14.7075 15.8814Z"
                fill="white"/>
        </svg>

      </GenericBtn>
      <p class="text-2xl ml-8 ">Kadena Bears</p>
    </div>
    <div class="pink-rectangle  w-[260px] h-[96px] rounded-2xl"></div>
  </div>
</template>

<script setup>

import GenericBtn from "../ui/GenericBtn";
</script>

<style scoped>
.pink-rectangle {
  background: #FC8AC2
}
</style>
<template>
  <div class="w-[172px] h-[240px]">
    <div>
      <img :src="imageUrl " class="cursor-pointer"/>
      <!--      <p>{{infoUrl}}</p>-->

    </div>
    <p class="text-sm text-[#ffffffa6] my-1.5"> {{ text }}</p>
    <p class="text-lg "> #{{ id }}</p>
  </div>
</template>

<script setup>
defineProps(['id', 'imageUrl', 'infoUrl', 'text', 'item'])


</script>

<style scoped>

</style>
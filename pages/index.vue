<template>
  <div>
    <CardList :cardList="data.cards"/>
  </div>
</template>

<script setup>

import CardList from "../components/card/List";

const {data} = await useFetch('/api/source')

</script>

<style scoped>

</style>
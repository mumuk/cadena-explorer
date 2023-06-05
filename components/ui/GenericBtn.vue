<template>
  <button
      class="flex justify-center items-center cursor-pointer bg-opacity-100 rounded-2xl right-10 top-10 text-white "
      :class="{isDisabled:disabled}"
      :disabled="disabled">
    <slot></slot>
  </button>
</template>

<script setup>
const {disabled} = defineProps(['disabled'])

</script>

<style scoped>
button {
  background: rgba(255, 255, 255, 0.15);
}

.isDisabled {
  background: rgba(255, 255, 255, 0);
}

</style>
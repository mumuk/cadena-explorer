<template>
  <div class="nav flex items-center h-[80%]">
    <div class="list-header">
      <div class="nav-item mr-6 bg-amber-300">
        <KadenaIcon/>
      </div>

      <div class="nav-item flex items-center">
        <CircleKIcon/>
        <span class="header-text-1">KDA</span>
        <div class=" ">
          <span class="header-text-2">$23.8</span>
          <span class="header-text-3">(+1.85%)</span>
        </div>
      </div>
    </div>

  </div>
</template>

<script setup>

import KadenaIcon from "./icons/KadenaIcon";
import CircleKIcon from "./icons/CircleKIcon";
</script>

<style scoped>

.nav {
  display: flex;
  align-items: center;
  height: 80px;
}

.list-header {
  display: flex;
  align-items: flex-end;
}

.nav-item {
  margin-right: 2rem;
}

.header-text-1 {
  margin-left: 0.5rem;
}

.header-text-2 {
  margin-left: 1rem;
  margin-right: .4rem;

}

.header-text-3 {
  color: #00FF85;
}
</style>
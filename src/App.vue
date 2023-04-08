<template>
  <div class="wrapper">
    <CustomNavbar/>
      <router-view/>
    <CustomFooter/>
  </div>

</template>

<script lang="ts" setup>

import CustomNavbar from "./components/app/navbar/CustomNavbar.vue";
import CustomFooter from "@/components/app/footer/CustomFooter.vue";
</script>

<style lang='sass'>
@import "@/assets/styles/_globals.sass"
.wrapper
  display: flex
  height: 100%
  flex-direction: column
  justify-content: space-between
  align-items: center
  border: 1px solid #1E2D3D
  position: relative
  border-radius: 20px
  background: $bg-color
</style>
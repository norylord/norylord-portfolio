<template>
  <section class="home">
    <div class="home__desc">
      <h2 class="home__desc-subtitle">Hi all. I am</h2>
      <h1 class="home__desc-title">Alexandr Pletnev</h1>
      <p class="home__desc-info"> > Front-end developer</p>

      <p class="home__desc-comment">// you can also see it on my Github page</p>
      <p class="home__desc-link">const githubLink = “https://github.com/Norylord”</p>
    </div>
    <div class="home__slider">
      <HomeSlider/>
    </div>
  </section>
</template>

<script lang="ts" setup>

import HomeSlider from "@/modules/home/components/HomeSlider.vue";
</script>

<style lang='sass'>
@import "@/assets/variables/_colors.sass"
.home
  display: flex
  max-width: 1400px
  width: 100%
  justify-content: space-around
  align-items: center
  padding: 0 32px
  &__slider
    flex: 1
    height: 600px
    align-items: center
    display: flex
    //box-shadow: 0px 99px 20px -63px rgb(1, 22, 39) inset, 0px -99px 20px -63px rgb(1, 22, 39) inset
    position: relative
    &:after
      content: ''
      width: 600px
      height: 600px
      position: absolute
      background: rgb(73,218,201)
      background: radial-gradient(circle, rgb(34, 100, 91) 0%, rgba(1, 22, 39, 0) 70%)
      background-repeat: no-repeat
      left: -100px
      top: -100px
      z-index: 0
      transform: rotate(30deg)
    &:before
      content: ''
      width: 600px
      height: 400px
      position: absolute
      background: rgb(73,218,201)
      background: radial-gradient(circle, rgba(77, 91, 206, 0.8) 0%, rgba(1, 22, 39, 0) 50%)
      background-repeat: no-repeat
      left: 200px
      top: 280px
      z-index: 0
      transform: rotate(30deg)
  &__desc
    flex: 1
    &-title
      font-size: 62px
      font-weight: 400
    &-subtitle
      font-size: 18px
      font-weight: 400
    &-info
      color: $text-link
      font-size: 32px
      font-weight: 400
    &-comment
      color: $text-lightgray
      margin-top: 80px
      margin-bottom: 8px
    &-link
      color: $text-link
      font-weight: 400
</style>
<template>
  <footer class="footer">
    <div class="footer__section">
      <div class="footer__section-item footer-title">
        find me in
      </div>
    </div>
    <div class="footer__section">
      <div class="footer__section-item footer-link">
        _telegram
      </div>
      <div class="footer__section-item footer-link">
        _vk
      </div>
    </div>
    <div class="footer__section">
      <div class="footer__section-item footer-contact footer-link">
        _github
      </div>
    </div>
  </footer>
</template>

<script lang="ts" setup>

</script>

<style lang='sass'>
@import "@/assets/variables/_colors.sass"
.footer
  display: flex
  width: 100%
  justify-content: space-between
  &__section
    display: flex
    border-top: 1px solid #1e2d3d
    &:nth-child(2)
      flex: 1
      border-left: 1px solid #1e2d3d
      border-right: 1px solid #1e2d3d
    &-item
      color: $text-lightgray
      padding: 16px 32px

  &-title
    flex: 1
    text-align: left
    cursor: default
  &-contact
    flex: 1
    text-align: left
  &-link
    cursor: pointer
    transition: .3s
    &:hover
      background: #1e2d3d
    &:nth-child(2)
      border-left: 1px solid #1e2d3d
      border-right: 1px solid #1e2d3d
    &:nth-child(3)
      border-right: 1px solid #1e2d3d
.active
  color: $text-default
  border-bottom: 2px solid #FEA55F
</style>
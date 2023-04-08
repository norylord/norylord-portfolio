<template>
  <div class="actions">
    <img :class="{'active-action' : activeTab === 'professional'}" @click="changeAction('professional')" class="actions__icon" src="@/assets/icons/professional-info-icon.svg" alt="">
    <img :class="{'active-action' : activeTab === 'personal'}" @click="changeAction('personal')" class="actions__icon" src="@/assets/icons/personal-info-icon.svg" alt="">
    <img :class="{'active-action' : activeTab === 'hobbies'}" @click="changeAction('hobbies')" class="actions__icon" src="@/assets/icons/hobbies-icon.svg" alt="">
  </div>
</template>

<script lang="ts" setup>
import {defineEmits, defineProps} from 'vue'

interface IProps {
  activeTab: 'professional' | 'personal' | 'hobbies'
}

const props = defineProps<IProps>()

const emit = defineEmits(['setAction'])
const changeAction = (value?: string) => {
  emit('setAction', value)
}
</script>

<style lang='sass'>
.actions
  height: 100%
  display: flex
  flex-direction: column
  padding: 20px 22px
  border-right: 1px solid #1e2d3d
  &__icon
    filter: invert(46%) sepia(51%) saturate(276%) hue-rotate(169deg) brightness(90%) contrast(83%)
    margin-bottom: 40px
    opacity: .4
    cursor: pointer
    transition: opacity .2s ease-in-out

.active-action
  opacity: 1
</style>
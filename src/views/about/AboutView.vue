<template>
  <section class="about">
    <AboutActions @set-action="changeTab" :active-tab="state.activeTab"/>
  </section>
</template>

<script lang="ts" setup>

import AboutActions from "@/components/app/about/AboutActions.vue";
import {reactive} from "vue";

interface IState {
  activeTab: 'professional' | 'personal' | 'hobbies'
}

const state = reactive<IState>({
  activeTab: "professional"
})

const changeTab = (label: 'professional' | 'personal' | 'hobbies') => {
  state.activeTab = label
}
</script>

<style lang='sass'>
.about
  width: 100%
  height: 100%
  display: flex

</style>
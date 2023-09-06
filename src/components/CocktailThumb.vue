<script setup>
import { RouterLink } from "vue-router";

const props = defineProps({
  cocktail: {
    type: Object,
    required: true,
  },
});
</script>

<template>
  <div class="root">
    <RouterLink :to="`/cocktails/${cocktail.idDrink}`">
      <div
        :style="`background-image: url(${cocktail.strDrinkThumb})`"
        class="pic"
      ></div>
    </RouterLink>
    <div class="name">{{ cocktail.strDrink }}</div>
  </div>
</template>

<style lang="sass" scoped>
@import '../assets/styles/main'
.root
  width: calc((100% - 76px)/3)
  margin-right: 18px
  padding-bottom: 30px

  &:nth-child(3n + 3)
    padding-right: 0

.pic
  width: 120px
  height: 120px
  margin: 0 auto
  background-repeat: no-repeat
  background-position: 50% 50%
  background-size: 100%

.name
  width: 100%
  white-space: nowrap
  overflow: hidden
  text-overflow: ellipsis
  padding-top: 15px
  letter-spacing: 0.1em
</style>
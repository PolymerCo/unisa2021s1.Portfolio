<template>
  <div class='all-content'>
    <section class='main-section sidebar'>
      <gallery-navigation/>
      <div class='flex-spacer'></div>
      <gallery-footer/>
    </section>
    <section class='main-section content'>
      <router-view/>
    </section>
  </div>
</template>

<script>

import GalleryNavigation from '@/components/GalleryNavigation.vue'
import GalleryFooter from '@/components/GalleryFooter.vue'

export default {
  name: 'App',
  components: { GalleryNavigation, GalleryFooter }
}

</script>

<style lang="sass">

@import 'assets/style/reset.css'
@import 'assets/style/fonts.css'
@import 'assets/style/theme'

*
  font-family: 'Noto Sans JP', sans-serif

a
  color: $body-font-color-alt
  text-decoration: none

hr
  width: 30%
  border: none
  border-top: 1px dashed #acacac
  margin: 30px 0

div.flex-spacer
  flex: 1

div.all-content
  display: flex
  flex-wrap: wrap

  section.main-section
    display: flex
    flex-direction: column
    padding: 38px

    &.sidebar
      width: 380px
      max-width: 100vw
      display: flex
      flex-direction: column
      border-right: 1px dashed #c8c8c8

    &.content
      flex: 1
      padding: 84px

</style>

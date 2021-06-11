<template>
  <div class='all-content'>
    <section id='t' class='main-section sidebar'>
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
  components: { GalleryNavigation, GalleryFooter },
  watch: {
    $route () {
      document.getElementById('t').scrollIntoView()
    }
  }
}

</script>

<style lang="sass">

@import 'assets/style/reset.css'
@import 'assets/style/fonts.css'
@import 'assets/style/theme'

html
  scroll-behavior: smooth

a
  color: $body-font-color-alt
  text-decoration: none

*
  color: $body-font-color

body
  background-color: $background-color

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
  min-height: 100vh

  section.main-section
    display: flex
    flex-direction: column
    padding: 38px
    max-width: 1000px
    margin: 0 auto

    &.sidebar
      width: 410px
      max-width: 100vw
      display: flex
      flex-direction: column
      border-right: 1px dashed #c8c8c8

    &.content
      flex: 1
      padding: 84px

</style>

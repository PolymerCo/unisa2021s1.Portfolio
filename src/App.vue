<template>
  <!-- <div id="nav">
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link>
  </div> -->
  <div class='all-content'>
    <section class='main-section sidebar'>
      <gallery-navigation/>
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

div.all-content
  display: flex
  flex-wrap: wrap

  section.main-section

    &.sidebar
      width: 360px
      max-width: 100vw

    &.content
      flex: 1

</style>

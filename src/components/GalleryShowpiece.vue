<template>
  <div class='showpiece-item'>
    <div v-if="project == 'ppsh41'">
      <ppsh-gallery/>
    </div>
    <div v-else-if="project == 'blueyeti'">
      <blueyeti-gallery/>
    </div>
    <div v-else>
      <router-link to='/'>Go home</router-link>
    </div>
  </div>
</template>

<script>
import BlueyetiGallery from './projects/BlueyetiGallery.vue'
import PpshGallery from './projects/PpshGallery.vue'

export default {
  props: ['project'],
  name: 'GalleryShowpiece',
  components: { PpshGallery, BlueyetiGallery }
}
</script>

<style lang="sass" scoped>
  div.showpiece-item
    width: 100%
    height: 100%
    max-width: 1000px
    margin: 0 auto
</style>

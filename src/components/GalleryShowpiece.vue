<template>
  <div class='showpiece-item'>
    <div v-if="project === 'ppsh41'">
      <ppsh-gallery/>
    </div>
    <div v-else-if="project === 'blueyeti'">
      <blueyeti-gallery/>
    </div>
    <div v-else-if="project === 'vikingsword'">
      <viking-sword/>
    </div>
    <div v-else-if="project === 'missile'">
      <missile-gallery/>
    </div>
    <div v-else>
      <router-link to='/'>Go home</router-link>
    </div>
  </div>
</template>

<script>
import BlueyetiGallery from '@/components/projects/BlueyetiGallery.vue'
import PpshGallery from '@/components/projects/PpshGallery.vue'
import VikingSword from '@/components/projects/VikingSword'
import MissileGallery from '@/components/projects/MissileGallery'

export default {
  props: ['project'],
  name: 'GalleryShowpiece',
  components: { MissileGallery, VikingSword, PpshGallery, BlueyetiGallery }
}
</script>

<style lang="sass" scoped>
  div.showpiece-item
    width: 100%
    height: 100%
    max-width: 1000px
    margin: 0 auto
</style>

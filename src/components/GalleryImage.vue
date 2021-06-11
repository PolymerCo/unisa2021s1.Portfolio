
<template>
  <div class='image-container'>
    <img class='loading' src='/image/ui/loader.gif'/>
    <img class='showcase-preloader' @load="setLoaded()" :src="'/image/projects/' + $route.params.id + '/' + $route.params.image + '.png'">
    <img class='image' :is-loaded='isLoaded' :src="'/image/projects/' + $route.params.id + '/' + $route.params.image + '.png'">
  </div>
</template>

<script>
export default {
  name: 'GalleryImage',
  components: [],
  data () {
    return {
      hasLoaded: false
    }
  },
  methods: {
    setLoaded () {
      this.hasLoaded = true
    }
  },
  computed: {
    isLoaded () {
      return this.hasLoaded
    }
  }
}
</script>

<style lang="sass" scoped>
  .image-container
    position: fixed
    top: 0
    left: 0
    width: 100vw
    height: 100vh
    background: rgba(0, 0, 0, 0.45)
    backdrop-filter: saturate(0.5)
    display: flex
    flex-direction: column
    justify-content: center

    .showcase-preloader
      display: none

    img
      max-width: calc(100vw - 120px)
      max-height: calc(100vh - 120px)
      margin: 0 auto
      box-shadow: 0 0 0 10px white, 0 0 12px 10px rgb(0 0 0 / 20%)

      transition: 200ms opacity ease-in-out

      &[is-loaded='false']
        opacity: 0

      &[is-loaded='true']
        opacity: 1
</style>

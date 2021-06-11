
<template>
  <div class='image-container' tabindex='-1' @keydown.esc='leave()'>
    <img class='loading' :is-loaded='isLoaded' src='/image/ui/loader.gif'/>
    <img class='showcase-preloader' @load="setLoaded()" :src="'/image/projects/' + $route.params.id + '/' + $route.params.image + '.png'">
    <div class='image-wrapper' v-if='isLoaded'>
      <img class='image' :is-loaded='isLoaded' :src="'/image/projects/' + $route.params.id + '/' + $route.params.image + '.png'">
      <router-link :to='"/gallery/" + $route.params.id'>Back to gallery</router-link>
      <a style='top: 64px; left: -182px' :href="'/image/projects/' + $route.params.id + '/' + $route.params.image + '.png'" target="_blank">View external</a>
    </div>
  </div>
</template>

<script>
export default {
  name: 'GalleryImage',
  components: [],
  updated () {
    const e = document.querySelector('.image-container')
    if (e != null && typeof (e[0]) !== 'undefined') {
      e[0].focus()
    }
  },
  data () {
    return {
      hasLoaded: false
    }
  },
  methods: {
    setLoaded () {
      this.hasLoaded = true
    },

    leave () {
      console.log('bye bye')
      this.$router.push('/gallery/' + this.$route.params.id)
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

    animation: 400ms ease-in forwards 'gallery-image-intro'

    .loading
      width: 72px
      background-color: white
      position: absolute
      margin: 0 auto
      top: 100px
      left: calc(50% - 36px)

      &[is-loaded='true']
        display: none

    .showcase-preloader
      display: none

    .image-wrapper
      width: fit-content
      margin: 0 auto
      position: relative

      a
        position: absolute
        top: 10px
        left: -192px
        padding: 8px 14px 8px 40px
        background: var(--body-font-color)
        color: var(--background-color)
        opacity: 0.8

        transition: 200ms opacity ease-in-out

        &::before
          content: '\3008'
          position: absolute
          left: 10px
          top: 8px

          transition: 200ms left ease-in-out

        &:hover
          opacity: 1

          &::before
            left: 6px

      img
        max-width: calc(100vw - 420px)
        max-height: calc(100vh - 120px)
        margin: 0 auto
        box-shadow: 0 0 0 10px white, 0 0 12px 10px rgb(0 0 0 / 20%)
        background-image: url('/image/ui/alpha_dark.bmp')

        transition: 200ms opacity ease-in-out

        &[is-loaded='false']
          opacity: 0

        &[is-loaded='true']
          opacity: 1

  @keyframes gallery-image-intro
    from
      opacity: 0
      transform: scale(0.8)
    to
      opacity: 1
      transform: scale(1)
</style>

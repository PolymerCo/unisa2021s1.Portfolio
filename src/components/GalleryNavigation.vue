<template>
  <div class='gallery-navigation-root'>
    <div class='header'>
      Oliver Mitchell
      <span class='sub-header'>@PolymerDesign</span>
    </div>
    <nav class='nav'>
      <router-link class='nav-link' to='/'>Gallery</router-link>
      <router-link class='nav-link' to='/about'>About</router-link>
      <router-link class='nav-link' to='/contact'>Contact</router-link>
      <br>
      <router-link class='nav-link' to='/gallery/ppsh_41'>PPSh-41</router-link>
      <router-link class='nav-link' to='/gallery/blue_yeti'>Blue Yeti</router-link>
      <router-link class='nav-link' to='/gallery/sub_console'>Sub Console</router-link>
      <router-link class='nav-link' to='/gallery/missile'>Missile</router-link>
    </nav>
  </div>
</template>

<script>

export default {
  name: 'GalleryNavigation',
  components: { },
  data () {
    return {

    }
  }
}
</script>

<style lang="sass" scoped>
  @import '@/assets/style/theme.sass'

  div.gallery-navigation-root
    padding: 35px 68px

    div.header
      font-family: 'Comfortaa', sans-serif
      font-size: 3.5em
      color: $header-font-color

      span.sub-header
        font-size: 0.3em
        display: inherit
        font-style: italic
        font-family: 'JetBrains Mono'

    nav.nav
      padding: 38px 0

      a.nav-link
        display: block
        color: black
        text-decoration: none
        margin: 0 0 14px
        font-size: 1.1em
        cursor: pointer
        position: relative
        width: fit-content
        padding: 0 6px
        margin-left: -6px
        color: $body-font-color

        &:not([aria-current='page'])::after
          content: ''
          width: 0%
          height: 2px
          left: 6px
          bottom: -3px
          background: $body-font-color
          position: absolute

          transition: 200ms width ease-in-out

        &:not([aria-current='page']):hover::after
          width: calc(100% - 12px)

        &[aria-current='page']
          background-color: $body-font-color
          color: $background-color
          box-shadow: 0 0 0 3px $body-font-color
        

</style>

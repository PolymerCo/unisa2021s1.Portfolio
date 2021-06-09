<template>
  <div class='gallery-navigation-root'>
    <div class='header'>
      Oliver Mitchell
      <span class='sub-header'>@PolymerDesign</span>
    </div>
    <nav class='nav'>
      <router-link class='nav-link' to='/' icon='🖼️'>Gallery</router-link>
      <router-link class='nav-link' to='/about' icon='🧠'>About</router-link>
      <router-link class='nav-link' to='/contact' icon='📧'>Contact</router-link>
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
  @import '../assets/style/theme'

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
        font-family: 'JetBrains Mono', monospace

    nav.nav
      padding: 38px 0

      a.nav-link
        display: block
        text-decoration: none
        font-size: 1.1em
        cursor: pointer
        position: relative
        width: fit-content
        padding: 0 6px 0 32px
        margin: 0 0 14px -6px
        color: $body-font-color

        &::before
          content: attr(icon)
          position: absolute
          left: 4px
          bottom: 2px

        &:not([aria-current='page'])::after
          content: ''
          width: 0
          height: 1.5px
          left: 32px
          bottom: -3px
          background: $body-font-color
          position: absolute

          transition: 200ms width ease-in-out

        &:not([aria-current='page']):hover::after
          width: calc(100% - 38px)

        &[aria-current='page']
          background-color: $body-font-color
          color: $background-color
          box-shadow: 0 0 0 3px $body-font-color

        &:not([icon])
          padding: 0 6px

        &:not([icon]):not([aria-current='page'])::after
          left: 6px
        &:not([icon]):not([aria-current='page']):hover::after
          width: calc(100% - 12px)
</style>

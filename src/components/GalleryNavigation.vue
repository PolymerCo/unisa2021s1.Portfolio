<template>
  <div class='gallery-navigation-root'>
    <div class='header'>
      Oliver Mitchell
      <span class='sub-header'>3D Artist and Developer</span>
      <div class='contact-pins'>
        <a target='_blank' href='https://github.com/PolymerDesign'><img alt='github logo' src='/image/ui/github.svg'></a>
        <a target='_blank' href='https://www.linkedin.com/in/dev-olivermitchell'><img alt='linked in logo' src='/image/ui/linkedin.png'></a>
        <a target='_blank' href='mailto:oliver@polymerdesign.com.au'><img alt='email icon' src='/image/ui/email.png'></a>
      </div>
    </div>
    <nav class='nav'>
      <router-link class='nav-link' to='/' icon='🖼️' display-text='Gallery'><p>Gallery</p></router-link>
      <router-link class='nav-link' to='/about' icon='🧠' display-text='About'><p>About</p></router-link>
      <hr>
      <router-link class='nav-link project' to='/gallery/ppsh41' icon='#' display-text='PPSh41'><p>PPSh41</p></router-link>
      <router-link class='nav-link project' to='/gallery/blueyeti' icon='#' display-text='BlueYeti'><p>BlueYeti</p></router-link>
      <router-link class='nav-link project' to='/gallery/subconsole' icon='#' display-text='SubmarineConsole'><p>SubmarineConsole</p></router-link>
      <router-link class='nav-link project' to='/gallery/missile' icon='#' display-text='MissileLauncher'><p>MissileLauncher</p></router-link>
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

  div.contact-pins
    display: flex

    a
      height: 24px
      margin: 6px

      img
        width: 100%
        height: 100%

  div.gallery-navigation-root
    padding: 35px 68px
    height: 100%

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
      position: sticky
      top: 0
      padding: 62px 0 18px
      opacity: 0.75

      transition: 400ms opacity

      &:hover
        opacity: 1

      a.nav-link
        display: block
        text-decoration: none
        font-size: 1.1em
        cursor: pointer
        position: relative
        width: fit-content
        padding: 0 6px 0 32px
        margin: 0 0 14px -6px

        p
          color: $body-font-color

        &::before
          content: attr(icon)
          position: absolute
          left: 4px
          bottom: 2px
          overflow: hidden
          z-index: 20
          font-weight: bold

        &:not([aria-current='page']) p::after
          content: ' '
          width: 0
          height: 1.5px
          left: 32px
          bottom: -3px
          background: $body-font-color
          position: absolute

          transition: 200ms width ease-in-out

        &:not([aria-current='page']):hover p::after
          width: calc(100% - 38px)

        &[aria-current='page']::after
          content: attr(display-text)
          position: absolute
          top: -2px
          left: 0
          width: 0
          height: calc(100% + 4px)
          background-color: $body-font-color
          color: $background-color
          padding-left: 32px
          padding-top: 2px
          z-index: 10
          overflow: hidden

          animation: 400ms ease-in-out forwards nav-link-selected-entry

        &:not([icon])
          padding: 0 6px

        &:not([icon]):not([aria-current='page']) p::after
          left: 6px

        &:not([icon]):not([aria-current='page']):hover p::after
          width: calc(100% - 12px)

        &.project
          transform: translateX(-1px)

        &.project::before
          left: 12px
          bottom: 0

  @keyframes nav-link-selected-entry
    0%
      width: 32px
      opacity: 0
    50%
      opacity: 1
    60%
      width: 32px
    100%
      width: 100%

</style>

<template>
  <article class='showcase-container'>
    <router-link to='/gallery/ppsh41'>
      <div class='showcase-entry'>
        <div class='showcase-photo-container'>
          <img class='image-loader' src='/image/projects/ppsh41/Ppsh41_Unreal_Full_1.png' @load='setImageLoaded($event)'>

          <div class='showcase-photo' v-bind:is-loaded='isImageLoaded("/image/projects/ppsh41/Ppsh41_Unreal_Full_1.png")' style='background-image: url("/image/projects/ppsh41/Ppsh41_Unreal_Full_1.png")'></div>
        </div>
        <div class='showcase-sub-photo-container'>
          <img class='image-loader' @click='gotoGallery("ppsh41")' src='/image/projects/ppsh41/Ppsh41_Unreal_Magazine_1.png' @load='setImageLoaded($event)'/>
          <img class='image-loader' src='/image/projects/ppsh41/Ppsh41_Low_Poly_Full_Wireframe.png' @load='setImageLoaded($event)'>
          <img class='image-loader' src='/image/projects/ppsh41/Ppsh41_Low_Poly_Magazine_Wireframe.png' @load='setImageLoaded($event)'>

          <div class='showcase-photo sub-photo' v-bind:is-loaded='isImageLoaded("/image/projects/ppsh41/Ppsh41_Unreal_Magazine_1.png")' style='background-image: url("/image/projects/ppsh41/Ppsh41_Unreal_Magazine_1.png")'></div>
          <div class='showcase-photo sub-photo' v-bind:is-loaded='isImageLoaded("/image/projects/ppsh41/Ppsh41_Low_Poly_Full_Wireframe.png")' style='background-image: url("/image/projects/ppsh41/Ppsh41_Low_Poly_Full_Wireframe.png")'></div>
          <div class='showcase-photo sub-photo' v-bind:is-loaded='isImageLoaded("/image/projects/ppsh41/Ppsh41_Low_Poly_Magazine_Wireframe.png")' style='background-image: url("/image/projects/ppsh41/Ppsh41_Low_Poly_Magazine_Wireframe.png")'></div>
        </div>
      </div>
    </router-link>
    <div class='showcase-description'>
      <p class='showcase-title'>WW2 Soviet PPSh-41</p>
      <p class='showcase-article'>
        A game-ready Soviet WW2 sub-machine gun with both high-poly and low-poly representations; with full PBR material support.
      </p>
    </div>
    <router-link class='see-more-link' to='/gallery/ppsh41'><p>See more</p></router-link>
  </article>
  <hr/>
  <article class='showcase-container'>
    <router-link to='/gallery/blueyeti'>
      <div class='showcase-entry'>
        <div class='showcase-sub-photo-container'>
          <img class='image-loader' src='/image/projects/blueyeti/BlueYeti_Blender_White.png' @load='setImageLoaded($event)'/>
          <img class='image-loader' src='/image/projects/blueyeti/BlueYeti_Blender_Wireframe.png' @load='setImageLoaded($event)'>

          <div class='showcase-photo sub-photo' v-bind:is-loaded='isImageLoaded("/image/projects/blueyeti/BlueYeti_Blender_White.png")' style='background-image: url("/image/projects/blueyeti/BlueYeti_Blender_White.png")'></div>
          <div class='showcase-photo sub-photo' v-bind:is-loaded='isImageLoaded("/image/projects/blueyeti/BlueYeti_Blender_Wireframe.png")' style='background-image: url("/image/projects/blueyeti/BlueYeti_Blender_Wireframe.png")'></div>
        </div>
        <div class='showcase-photo-container'>
          <img class='image-loader' src='/image/projects/blueyeti/BlueYeti_Blender_Reference.png' @load='setImageLoaded($event)'>

          <div class='showcase-photo' v-bind:is-loaded='isImageLoaded("/image/projects/blueyeti/BlueYeti_Blender_Reference.png")' style='background-image: url("/image/projects/blueyeti/BlueYeti_Blender_Reference.png")'></div>
        </div>
      </div>
    </router-link>
    <div class='showcase-description'>
      <p class='showcase-title'>Blue Yeti Microphone</p>
      <p class='showcase-article'>
        The iconic Blue Yeti studio microphone re-imagined as a low polygon model.
      </p>
    </div>
    <router-link class='see-more-link' to='/gallery/blueyeti'><p>See more</p></router-link>
  </article>
  <hr/>
  <article class='showcase-container'>
    <router-link to='/gallery/vikingsword'>
      <div class='showcase-entry'>
        <div class='showcase-photo-container'>
          <img class='image-loader' src='/image/projects/vikingsword/Render_VikingSword_Front_Sideways.png' @load='setImageLoaded($event)'>

          <div class='showcase-photo' v-bind:is-loaded='isImageLoaded("/image/projects/vikingsword/Render_VikingSword_Front_Sideways.png")' style='background-image: url("/image/projects/vikingsword/Render_VikingSword_Front_Sideways.png")'></div>
        </div>
      </div>
    </router-link>
    <div class='showcase-description'>
      <p class='showcase-title'>Viking Sword</p>
      <p class='showcase-article'>
        Inspired by real life Scandanavian sword findings, with some artistic flourish.
      </p>
    </div>
    <router-link class='see-more-link' to='/gallery/vikingsword'><p>See more</p></router-link>
  </article>
  <hr/>
  <article class='showcase-container'>
    <router-link to='/gallery/ppsh41'>
      <div class='showcase-entry'>
        <div class='showcase-sub-photo-container'>
          <img class='image-loader' src='/image/projects/ppsh41/Ppsh41_Low_Poly_Magazine_Wireframe.png' @load='setImageLoaded($event)'>
          <div class='showcase-photo sub-photo' v-bind:is-loaded='isImageLoaded("/image/projects/ppsh41/Ppsh41_Unreal_Magazine_1.png")' style='background-image: url("/image/projects/ppsh41/Ppsh41_Unreal_Magazine_1.png")'></div>
        </div>
        <div class='showcase-photo-container'>
          <img class='image-loader' src='/image/projects/ppsh41/Ppsh41_Unreal_Full_1.png' @load='setImageLoaded($event)'>
          <div class='showcase-photo' v-bind:is-loaded='isImageLoaded("/image/projects/ppsh41/Ppsh41_Unreal_Full_1.png")' style='background-image: url("/image/projects/ppsh41/Ppsh41_Unreal_Full_1.png")'></div>
        </div>
      </div>
    </router-link>
    <div class='showcase-description'>
      <p class='showcase-title'>V-2 Missile</p>
      <p class='showcase-article'>
        Based on the WW2 German V-2 Missile. A low-poly rendition of the terrifying but inspiring technology that begun the space age.
      </p>
    </div>
    <router-link class='see-more-link' to='/gallery/missile'><p>See more</p></router-link>
  </article>
  <hr/>
</template>

<script>

// import router from '../router'

export default {
  name: 'Home',
  components: { },
  data () {
    return {
      loadedImages: []
    }
  },
  methods: {
    setImageLoaded (e) {
      this.loadedImages.push(e.target.getAttribute('src'))
    },
    isImageLoaded (url) {
      return this.loadedImages.includes(url)
    }
  }
}
</script>

<style lang="sass" scoped>
  @import '@/assets/style/theme'

  .image-loader
    display: none

  hr
    margin: 42px auto

  article.showcase-container
    border: 6px solid white

    a.see-more-link
      color: var(--body-font-color-alt)
      display: block
      margin: 28px 0 0
      text-align: center

      p
        position: relative
        display: inline
        margin: 0 auto

        &::before
          position: absolute
          content: '\3009'
          right: -24px
          top: 1px
          transition: 100ms right linear

        &:hover::before
          right: -28px

    div.showcase-entry
      height: 20vw
      min-height: 300px
      width: 100%
      display: flex

      div.showcase-photo
        background-size: cover
        background-position: center
        background-repeat: no-repeat
        cursor: pointer

        transition: 200ms box-shadow ease-in-out, 200ms border-radius ease-in-out, 200ms filter ease-in-out

        &[is-loaded='false']
          opacity: 1
          box-shadow: inset 0 0 0 10px white
          cursor: default
          background-image: url('/image/ui/loader.gif') !important
          background-size: 50px

        &[is-loaded='true']
          opacity: 1
          box-shadow: inset 0 0 0 4px white
          animation: 200ms ease-in-out forwards "showcase-photo-entry"
          filter: opacity(1)

        &[is-loaded='true']:hover
          box-shadow: inset 0 0 0 10px white
          filter: opacity(0.8)

      div.showcase-photo-container
        flex: 1

        div.showcase-photo
          height: 100%

      div.showcase-sub-photo-container
        flex-basis: 10vw
        min-width: 100px
        display: flex
        flex-direction: column

        div.showcase-photo
            flex: 1

    div.showcase-description
      font-family: 'Bitter', sans-serif

      p.showcase-title, p.showcase-article
        font-family: inherit
        padding: 0 80px
        text-align: center

      p.showcase-title
        display: block
        font-size: 1.7em
        margin: 26px auto
        width: fit-content
        background-color: $body-font-color
        color: $background-color

      p.showcase-article
        padding: 0 80px
        font-size: 1.2em
        line-height: 1.8em

  @keyframes showcase-photo-entry
    from
      opacity: 0
    to
      opacity: 1
</style>

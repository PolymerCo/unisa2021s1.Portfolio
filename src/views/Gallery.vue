<template>
  <gallery-showpiece :project="$route.params.id"/>
  <gallery-image v-if="$route.params.image != ''" :project="$route.params.id" :image="$route.params.image"/>
</template>

<script>
import GalleryShowpiece from '@/components/GalleryShowpiece.vue'
import GalleryImage from '@/components/GalleryImage.vue'

export default {
  name: 'Gallery',
  components: { GalleryShowpiece, GalleryImage }
}
</script>

<style lang="sass">
  @import '@/assets/style/theme'

  .gallery-header h1
    margin: 68px 0 15px
    font-family: 'Bitter', sans-serif
    color: $body-font-color
    font-size: 2em
    text-align: center

  .showpiece-item hr
    width: 50%
    margin: 54px auto

  .gallery-information
    display: flex
    flex-wrap: wrap
    margin-bottom: 48px

    .gallery-statistics, .gallery-description
      min-width: 240px

      .links
        text-align: center
        font-size: 0.8em
        font-style: italic
        margin-top: 46px
        line-height: 2

    .gallery-description
      flex: 1
      text-align: justify
      padding: 0 34px 0 0

      p
        font-family: 'Bitter', sans-serif
        margin: 25px 0
        line-height: 1.8

    .gallery-statistics
      padding: 20px

      table
        margin-bottom: 26px

        transition: 200ms opacity ease-in-out

        &.statistic-secondary
          opacity: 0.6

          &:hover
            opacity: 1

        th, td
          font-family: 'JetBrains Mono', monospace
          text-align: left
          padding: 3px 6px
          font-size: 0.9em

        td
          color: #606060

  .showcase-set
    width: 100%
    height: fit-content
    display: flex
    flex-wrap: wrap

    .showcase-preloader
      display: none

    .showcase-item
      height: 200px
      flex: 1

      transition: 500ms flex ease-in

      .showcase-image
        width: 100%
        height: 100%
        min-width: 100px
        background-size: cover
        background-position: center
        background-repeat: no-repeat
        opacity: 0.8

        transition: 200ms box-shadow ease-in-out

      &[is-loaded='false']
        opacity: 1
        pointer-events: none

        .showcase-image
          opacity: 1
          box-shadow: inset 0 0 0 10px white
          background-image: url('/image/ui/loader.gif') !important
          background-size: 50px

      &[is-loaded='true']
        animation: 200ms ease-in-out forwards "showcase-photo-entry"
        pointer-events: all

        .showcase-image
          position: relative
          box-shadow: inset 0 0 0 4px white
          cursor: pointer

          &::after
            content: ' '
            position: absolute
            opacity: 0
            top: 5px
            right: 5px
            width: 40px
            height: 40px
            background-image: url('/image/ui/expand.svg')
            background-size: contain
            background-repeat: no-repeat
            background-position: center
            background-color: $body-font-color

            transition: 200ms opacity ease-in-out, 200ms top ease-in-out, 200ms right ease-in-out

          &:not([item-desc=''])::before
            content: attr(item-desc)
            opacity: 0
            position: absolute
            left: 10px
            bottom: 10px
            width: calc(100% - 20px)
            height: fit-content
            z-index: 10
            color: white
            background-color: rgba(0, 0, 0, 0.5)
            font-size: 0.8em
            padding: 5px
            font-family: 'Bitter', sans-serif
            font-style: italic
            text-align: center

            transition: 200ms opacity ease-in-out

          &:hover
            opacity: 1
            box-shadow: inset 0 0 0 10px white

            &::before
              opacity: 1

            &::after
              opacity: 1
              top: 15px
              right: 15px

  @keyframes showcase-photo-entry
    from
      opacity: 0
    to
      opacity: 1
</style>

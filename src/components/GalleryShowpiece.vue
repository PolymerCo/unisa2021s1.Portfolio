<template>
  <div class='showpiece-item'>
    {{ project }}
  </div>
</template>

<script>

export default {
  props: ['project', 'description'],
  name: 'GalleryShowpiece',
  components: { }
}
</script>

<style lang="sass" scoped>
  div.showpiece-item
    width: 140px
    height: 140px
    background-color: cornflower
</style>

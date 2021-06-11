<template>
  <div class='showcases'>
    <div class='showcase-set'>
      <div class='showcase-item' :is-loaded="isLoaded(item.id)" :item-name='item.id' v-for='item in top_gallery' :key='item.id'>
        <img class="showcase-preloader" @load="setLoaded(item.id)" :src="'/image/projects/blueyeti/' + item.id + '.png'">
        <router-link :to='"/gallery/blueyeti/" + item.id'><div class='showcase-image' :item-desc="item.desc" :is-loaded="isLoaded(item.id)" :style="{ backgroundImage: 'url(&quot;/image/projects/blueyeti/' + item.id + '.png&quot;)' }"></div></router-link>
      </div>
    </div>
  </div>

  <div class='gallery-header'>
    <h1>BlueYeti Studio Microphone</h1>
  </div>

  <section class='gallery-information'>
    <article class='gallery-description'>
      <p>
        My main inspiration for this artwork was my childhood of games set in the World Wars. This weapon was iconic thoughout
        both history and video games, being the main weapon during the Soviet spearhead against Germany.
      </p>
      <p>
        The weapon made for hard modelling, with many small nooks and details. One particular pain point being the cooling vents
        on the barrel sheath. The weapon is seperated into two parts, where the magazine is detachable and is fully capable of
        being an asset by itself.
      </p>
    </article>
    <article class='gallery-statistics'>
      <table>
        <tr>
          <th>Vertices</th>
          <th>Triangles</th>
        </tr>
        <tr>
          <td>4,660</td>
          <td>8,916</td>
        </tr>
      </table>
    </article>
  </section>
</template>

<script>

export default {
  props: [],
  name: 'BlueyetiGallery',
  components: { },
  data () {
    return {
      loaded_images: [],
      top_gallery: [
        {
          id: 'BlueYeti_Blender_Reference',
          desc: 'UE render of the full weapon'
        }, {
          id: 'BlueYeti_Blender_White',
          desc: 'UE render of the magazine'
        }, {
          id: 'BlueYeti_Blender_White_2',
          desc: 'Full weapon high-poly render'
        }, {
          id: 'BlueYeti_Blender_Wireframe',
          desc: 'Full weapon low-poly render'
        }, {
          id: 'BlueYeti_Blender_Layout',
          desc: 'Magazine high-poly render'
        }
      ],

      setLoaded (image) {
        this.loaded_images.push(image)
      },

      isLoaded (image) {
        return this.loaded_images.includes(image)
      }
    }
  }
}
</script>

<style lang="sass" scoped>
  .showcase-item[item-name='BlueYeti_Blender_Reference']
    flex-basis: 100%

    transition: 200ms height ease-in

    &[is-loaded='true']:hover
      flex-basis: 100%
</style>

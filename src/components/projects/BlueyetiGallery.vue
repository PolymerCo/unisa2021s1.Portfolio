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
        Blue™ are known for making fantastic microphones and other audio gear. When thinking of a complex topology to re-create,
        the Blue™ Yeti™ came to mind.
      </p>
      <p>
        Most of the topology is quite simple for the model, however the stand offered some challenge. It's unusual curves mean that
        simple extrusion modelling cant be used, and freehand vertex mapipulation must be used instead. This was the primary tool
        for recreating the topology, and I feel it worked quite well.
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

      <div class='links'>
        Download <a class='see-more-link' href='https://github.com/PolymerDesign/unisa2021s1.Models/tree/master/Blue%20Yeti' target='_blank'>here</a>
        <p>I'm under the <a href='https://choosealicense.com/licenses/mit/' target='_blank'>MIT</a> licence!</p>
      </div>
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
          desc: 'Grey shaded render'
        }, {
          id: 'BlueYeti_Blender_White',
          desc: 'Grey shaded front view'
        }, {
          id: 'BlueYeti_Blender_White_Rear',
          desc: 'Gray shaded rear view'
        }, {
          id: 'BlueYeti_Blender_Wireframe',
          desc: 'Wireframe render'
        }, {
          id: 'BlueYeti_Blender_Layout',
          desc: 'UV layout of microphone'
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

</style>

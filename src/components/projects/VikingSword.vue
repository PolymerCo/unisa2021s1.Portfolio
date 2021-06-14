<template>
  <div class='showcases'>
    <div class='showcase-set short-showcase'>
      <div class='showcase-item' :is-loaded="isLoaded(item.id)" :item-name='item.id' v-for='item in top_gallery' :key='item.id'>
        <img class="showcase-preloader" @load="setLoaded(item.id)" :src="'/image/projects/vikingsword/' + item.id + '.png'">
        <router-link :to='"/gallery/vikingsword/" + item.id'><div class='showcase-image side-sword-alt' :item-desc="item.desc" :is-loaded="isLoaded(item.id)" :style="{ backgroundImage: 'url(&quot;/image/projects/vikingsword/' + item.id + '.png&quot;)', backgroundPositionY: 'calc(50% - -8px)' }"></div></router-link>
      </div>
    </div>
  </div>
  <div class='showcases tall-showcase'>
    <div class='showcase-set'>
      <div class='showcase-item' :is-loaded="isLoaded(item.id)" :item-name='item.id' v-for='item in lower_gallery' :key='item.id'>
        <img class="showcase-preloader" @load="setLoaded(item.id)" :src="'/image/projects/vikingsword/' + item.id + '.png'">
        <router-link :to='"/gallery/vikingsword/" + item.id'><div class='showcase-image' :item-desc="item.desc" :is-loaded="isLoaded(item.id)" :style="{ backgroundImage: 'url(&quot;/image/projects/vikingsword/' + item.id + '.png&quot;)' }"></div></router-link>
      </div>
    </div>
  </div>
  <div class='showcases'>
    <div class='showcase-set short-showcase'>
      <div class='showcase-item' :is-loaded="isLoaded(item.id)" :item-name='item.id' v-for='item in mid_gallery' :key='item.id'>
        <img class="showcase-preloader" @load="setLoaded(item.id)" :src="'/image/projects/vikingsword/' + item.id + '.png'">
        <router-link :to='"/gallery/vikingsword/" + item.id'><div class='showcase-image side-sword-alt' :item-desc="item.desc" :is-loaded="isLoaded(item.id)" :style="{ backgroundImage: 'url(&quot;/image/projects/vikingsword/' + item.id + '.png&quot;)', backgroundPositionY: 'calc(50% - -8px)' }"></div></router-link>
      </div>
    </div>
  </div>

  <div class='gallery-header'>
    <h1>Viking (Scandanavian) Sword</h1>
  </div>

  <section class='gallery-information'>
    <article class='gallery-description'>
      <p>
        Ancient Scandanavian swords have always been facinating to me, especially since learning more about norse mythology
        and learning the importantance of war to the Scandanavians. This sword is based from real findings, however has had
        some artisic embelishments added; such as the use of folded steel for the blade.
      </p>
      <p>
        A unique element of this model is the hammered metal decals within the gard and pommel, this effect was achieved
        procedurally using an inverted procedural stucci texture mixed with a displacement map. To properly demonstrate
        the method, see below for an example render.
      </p>
    </article>
    <article class='gallery-statistics'>
      <table>
        <tr>
          <th>Vertices</th>
          <th>Triangles</th>
        </tr>
        <tr>
          <td>523,955</td>
          <td>1,040,978</td>
        </tr>
      </table>

      <div class='links'>
        Download <a class='see-more-link' href='https://github.com/PolymerDesign/unisa2021s1.Models/tree/master/Viking%20Sword' target='_blank'>here</a>
        <p>I'm under the <a href='https://choosealicense.com/licenses/mit/' target='_blank'>MIT</a> licence!</p>
      </div>
    </article>
  </section>

  <div class='showcases tall-showcase'>
    <div class='showcase-set'>
      <div class='showcase-item' :is-loaded="isLoaded(item.id)" :item-name='item.id' v-for='item in underneath_gallery' :key='item.id'>
        <img class="showcase-preloader" @load="setLoaded(item.id)" :src="'/image/projects/vikingsword/' + item.id + '.png'">
        <router-link :to='"/gallery/vikingsword/" + item.id'><div class='showcase-image' :item-desc="item.desc" :is-loaded="isLoaded(item.id)" :style="{ backgroundImage: 'url(&quot;/image/projects/vikingsword/' + item.id + '.png&quot;)' }"></div></router-link>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  props: [],
  name: 'VikingSword',
  components: { },
  data () {
    return {
      loaded_images: [],
      top_gallery: [
        {
          id: 'Render_VikingSword_Front_Sideways',
          desc: 'Blender beauty render'
        }
      ],

      mid_gallery: [
        {
          id: 'Render_VikingSword_Wireframe',
          desc: 'Wireframe shot of the sword'
        }
      ],

      lower_gallery: [
        {
          id: 'Render_VikingSword_Front',
          desc: 'Blender beauty render'
        },
        {
          id: 'Render_VikingSword_Grip',
          desc: 'Beauty render of the grip'
        },
        {
          id: 'Render_VikingSword_Grip_Wireframe',
          desc: 'Blender beauty render'
        },
        {
          id: 'Render_VikingSword_White',
          desc: 'Grey shaded Blender render'
        }
      ],

      underneath_gallery: [
        {
          id: 'Render_VikingSword_Battered_Copper',
          desc: 'Example material for battered Copper'
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
  .side-sword-alt
    background-position-y: calc(50% - -8px)

  .tall-showcase .showcase-item
    height: 325px

  .short-showcase .showcase-item
    height: 125px
</style>

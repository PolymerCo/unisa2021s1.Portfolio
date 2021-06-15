<template>
  <div class='showcases'>
    <div class='showcase-set short-showcase'>
      <div class='showcase-item' :is-loaded="isLoaded(item.id)" :item-name='item.id' v-for='item in top_gallery' :key='item.id'>
        <img class="showcase-preloader" @load="setLoaded(item.id)" :src="'/image/projects/missile/' + item.id + '.png'">
        <router-link :to='"/gallery/missile/" + item.id'><div class='showcase-image' :item-desc="item.desc" :is-loaded="isLoaded(item.id)" :style="{ backgroundImage: 'url(&quot;/image/projects/missile/' + item.id + '.png&quot;)', backgroundPositionY: 'calc(50% - -8px)' }"></div></router-link>
      </div>
    </div>
  </div>
  <div class='showcases tall-showcase'>
    <div class='showcase-set'>
      <div class='showcase-item' :is-loaded="isLoaded(item.id)" :item-name='item.id' v-for='item in lower_gallery' :key='item.id'>
        <img class="showcase-preloader" @load="setLoaded(item.id)" :src="'/image/projects/missile/' + item.id + '.png'">
        <router-link :to='"/gallery/missile/" + item.id'><div class='showcase-image' :item-desc="item.desc" :is-loaded="isLoaded(item.id)" :style="{ backgroundImage: 'url(&quot;/image/projects/missile/' + item.id + '.png&quot;)' }"></div></router-link>
      </div>
    </div>
  </div>

  <div class='gallery-header'>
    <h1>German V-2 Rocket</h1>
  </div>

  <section class='gallery-information'>
    <article class='gallery-description'>
      <p>
        The German V-2 Rocket was an experimental program in WW2, the aim was to achieve ICBM like capabilities. The rockets
        proved fairly ineffective at their role, however the engineering behind the technology was extraordinary for the time.
        This rocket inspired both space-age technology and popular fictions, such as the Steamers in Orwell's 1984.
      </p>
      <p>
        While having simple topographic details, this model was fun and interesting to create. The unique patterns and texturing
        on the rocket made for an interesting challenge.
      </p>
    </article>
    <article class='gallery-statistics'>
      <table>
        <tr>
          <th>Vertices</th>
          <th>Triangles</th>
        </tr>
        <tr>
          <td>1,747</td>
          <td>3,450</td>
        </tr>
      </table>

      <div class='links'>
        Download <a class='see-more-link' href='https://github.com/PolymerDesign/unisa2021s1.Models/tree/master/V-2%20Rocket' target='_blank'>here</a>
        <p>I'm under the <a href='https://choosealicense.com/licenses/mit/' target='_blank'>MIT</a> licence!</p>
      </div>
    </article>
  </section>
</template>

<script>

export default {
  props: [],
  name: 'MissileGallery',
  components: { },
  data () {
    return {
      loaded_images: [],
      top_gallery: [
        {
          id: 'Blender_Missile_Upright_Below',
          desc: 'Blender beauty render'
        }
      ],

      lower_gallery: [
        {
          id: 'Blender_Missile_Upright_Render',
          desc: 'Blender beauty render'
        },
        {
          id: '2_Blender_Missile_Upright',
          desc: 'Beauty render of the grip'
        },
        {
          id: '0_Blender_Missile_Wireframe',
          desc: 'Blender beauty render'
        },
        {
          id: '1_Blender_Missile_Grey',
          desc: 'Grey shaded Blender render'
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
.tall-showcase .showcase-item
  height: 325px
</style>

<template>
  <div class='showcases'>
    <div class='showcase-set'>
      <div class='showcase-item' :is-loaded="isLoaded(item.id)" :item-name='item.id' v-for='item in top_gallery' :key='item.id'>
        <img class="showcase-preloader" @load="setLoaded(item.id)" :src="'/image/projects/ppsh41/' + item.id + '.png'">
        <router-link :to='"/gallery/ppsh_41/" + item.id'><div class='showcase-image' :item-desc="item.desc" :is-loaded="isLoaded(item.id)" :style="{ backgroundImage: 'url(&quot;/image/projects/ppsh41/' + item.id + '.png&quot;)' }"></div></router-link>
      </div>
    </div>
  </div>

  <div class='gallery-header'>
    <h1>Soviet PPSh-41 Sub Machine Gun</h1>
  </div>

  <section class='gallery-information'>
    <article class='gallery-description'>
      <p>
        My main inspiration for this artwork was my childhood of playing games set in the World Wars. This weapon is iconic thoughout
        both history and video games, being a primary weapon of the infantry during the Soviet spearhead against Germany.
      </p>
      <p>
        The weapon made for hard modelling, with many small nooks and details. One particular pain point being the cooling vents
        on the barrel sheath. The weapon is seperated into two parts, where the magazine is detachable and is fully capable of
        being an asset by itself.
      </p>
      <p>
        The models have all required PBR textures to be 'game ready', they both have great detail and low poly counts.
      </p>
    </article>
    <article class='gallery-statistics'>
      <table>
        <tr>
          <th>Low-Poly</th>
          <th>Vertices</th>
          <th>Triangles</th>
        </tr>
        <tr>
          <td>Everything</td>
          <td>2,622</td>
          <td>5,096</td>
        </tr>
        <tr>
          <td>Magazine</td>
          <td>460</td>
          <td>862</td>
        </tr>
      </table>

      <table class='statistic-secondary'>
        <tr>
          <th>High-Poly</th>
          <th>Vertices</th>
          <th>Triangles</th>
        </tr>
        <tr>
          <td>Everything</td>
          <td>442,505</td>
          <td>883,371</td>
        </tr>
        <tr>
          <td>Magazine</td>
          <td>284,871</td>
          <td>568,784</td>
        </tr>
      </table>
      <div class='links'>
        Download <a class='see-more-link' href='https://github.com/PolymerDesign/unisa2021s1.Models/tree/master/PPSh-41' target='_blank'>here</a>
        <p>I'm under the <a href='https://choosealicense.com/licenses/mit/' target='_blank'>MIT</a> licence!</p>
      </div>
    </article>
  </section>

  <div class='showcases'>
    <div class='showcase-set'>
      <div class='showcase-item' :is-loaded="isLoaded(item.id)" :item-name='item.id' v-for='item in bottom_gallery' :key='item.id'>
        <img class="showcase-preloader" @load="setLoaded(item.id)" :src="'/image/projects/ppsh41/' + item.id + '.png'">
        <router-link :to='"/gallery/ppsh41/" + item.id'><div class='showcase-image' :item-desc="item.desc" :is-loaded="isLoaded(item.id)" :style="{ backgroundImage: 'url(&quot;/image/projects/ppsh41/' + item.id + '.png&quot;)' }"></div></router-link>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  props: [],
  name: 'PpshGallery',
  components: { },
  data () {
    return {
      loaded_images: [],
      top_gallery: [
        {
          id: 'Ppsh41_Unreal_Full_1',
          desc: 'UE render of the full weapon'
        }, {
          id: 'Ppsh41_Unreal_Magazine_1',
          desc: 'UE render of the magazine'
        }, {
          id: 'Ppsh41_High_Poly_Full_Grey',
          desc: 'Full weapon high-poly render'
        }, {
          id: 'Ppsh41_Low_Poly_Full_Wireframe',
          desc: 'Full weapon low-poly wireframe'
        }, {
          id: 'Ppsh41_High_Poly_Magazine_Grey',
          desc: 'Magazine high-poly render'
        }, {
          id: 'Ppsh41_Low_Poly_Magazine_Wireframe',
          desc: 'Magazine low-poly wireframe'
        }
      ],

      bottom_gallery: [
        {
          id: 'OM_Bake_Ppsh41_Diffuse',
          desc: ''
        }, {
          id: 'OM_Bake_Ppsh41_AO',
          desc: ''
        }, {
          id: 'OM_Bake_Ppsh41_Metallic',
          desc: ''
        }, {
          id: 'OM_Bake_Ppsh41_Normals',
          desc: ''
        }, {
          id: 'OM_Bake_Ppsh41_Roughness',
          desc: ''
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
  .showcase-item[item-name='Ppsh41_Unreal_Full_1']
    flex-basis: 100%

    transition: 200ms height ease-in

    &[is-loaded='true']:hover
      flex-basis: 100%

    .showcase-image
      background-position: 50% 34%
</style>

<template>
  <div class='about-banner'></div>
  <h3 class='title'>3d Artist & Developer, Adelaide, SA, Australia</h3>
  <div class='about-me'>
    <p>
      I'm currently studying a Bachelor of Software Engineering at UniSA. My main focus is software development for business,
      however my other passion is game development. From necessity I have learnt to love 3D design; especially the design of
      military game assets.
    </p>
    <p>
      As you may have seen, a lot of my designs are military focused. I currently work for Saab Australia focusing on naval
      projects, and military has always being a big interest for me. Hopefully I'll continue to design them, and will continue
      to relish in the final product!
    </p>
  </div>
  <div class='about-details'>
    <div class='about-3d'>
      <h3>3D Design</h3>
      <h4>Key Skills</h4>
      <ul>
        <li>Low-poly topology modeling</li>
        <li>Composition of PBR textures</li>
        <li>High to low topology translation</li>
        <li>Rigging</li>
        <li>Graphic design</li>
      </ul>
      <h4>Software</h4>
      <ul>
        <li>Photoshop<span class='proficiency'>excellent</span></li>
        <li>Unity 3D<span class='proficiency'>excellent</span></li>
        <li>Blender<span class='proficiency'>good</span></li>
        <li>Illustrator<span class='proficiency'>good</span></li>
        <li>Unreal<span class='proficiency'>novice</span></li>
      </ul>
    </div>
    <div class='about-dev'>
      <h3>Software Development</h3>
      <h4>Key Skills</h4>
      <ul>
        <li>Complex system design</li>
        <li>SOLID design principles</li>
        <li>Defence and commercial experience</li>
        <li>Large team projects</li>
        <li>Lead company-wide projects</li>
      </ul>
      <h4>Languages</h4>
      <ul>
        <li>C#<span class='proficiency'>excellent</span></li>
        <li>Java<span class='proficiency'>excellent</span></li>
        <li>Web (js/html/css)<span class='proficiency'>exellent</span></li>
        <li>C++<span class='proficiency'>good</span></li>
        <li>Python<span class='proficiency'>good</span></li>
        <li>Ada<span class='proficiency'>novice</span></li>
      </ul>
    </div>
  </div>
</template>

<script>

export default {
  name: 'About',
  components: { }
}
</script>

<style lang="sass" scoped>
  .about-banner
    width: 100%
    height: 200px
    background-image: url('/image/about_image.png')
    background-size: cover
    background-position: center

  .title
    padding: 22px 22px 0

  .about-me p, .about-details h3, .about-details h4, .about-details li
    font-family: 'Bitter', sans-serif

  .about-me
    margin-bottom: 12px
    line-height: 1.9

    p
      padding: 20px 20px 0

      &:first-of-type
        margin-top: 20px

      &:last-of-type
        margin-bottom: 20px

  .about-details
    display: flex

    > div
      flex: 1
      padding: 20px

      h3
        margin-bottom: 10px

      li
        list-style: none
        position: relative

        &::before
          content: '\3009'
          position: absolute
          left: -15px
          top: 6px
          font-size: 0.5em

      .proficiency
        font-style: italic
        margin-left: 7px
        color: var(--body-font-color-alt)
        font-size: 0.8em

</style>

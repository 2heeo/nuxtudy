<template>
  <div id="main">
    <Slider />
    <Menu />
    <ImageLink />
  </div>
</template>

<script>
  import Slider from '~/components/Slider';
  import Menu from '~/components/Menu';
  import ImageLink from '~/components/ImageLink.vue';

  export default {
    data() {
      return {
        name: 'Nuxt.js',
      }
    },
    components: {
      Slider,
      Menu,
      ImageLink
    }
  }
</script>

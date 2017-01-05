<template lang="pug">
#app
  h3.ui.center.aligned.header {{ title }}
  .ui.container.text
    .ui.segments(v-for="video in videos")
      .ui.segment
        .ui.embed(v-bind:data-source="video.source" v-bind:data-id="video.id" v-bind:data-placeholder="video.placeholder")

</template>

<script>
var semantic = require('semantic-ui-css/semantic.min.js')

export default {
  name: 'app',
  data () {
    return {
      title: 'Welcome to Your Vue.js App',
      videos: [
        {'source': 'youtube', 'id': 'O6Xo21L0ybE', 'placeholder': '//semantic-ui.com/images/image-16by9.png'},
        {'source': 'vimeo', 'id': '125292332', 'placeholder': '//semantic-ui.com/images/vimeo-example.jpg'},
      ]
    }
  },
  mounted: function() {
    $('.ui.embed').embed();
  }
}
</script>

<style src="semantic-ui-css/semantic.min.css"></style>

<template>
  <div id="app">
    <VideoJSRecord />
  </div>
</template>

<script>
import VideoJSRecord from './components/VideoJSRecord.vue'

export default {
  name: 'app',
  components: {
    VideoJSRecord
  }
}
</script>

<style>
/* change player background color */
#myVideo {
  background-color: #95DDF5;
}
</style>

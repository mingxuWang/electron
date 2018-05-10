<script>
export default {
  props: {
    message: {
      type: String
    }
  },
  data () {
    return {
      baseUrl: 'http://10.93.109.31:8002/tts?idx=1&cuid=speech&lan=zh&ctp=1&pdt=1&tex=',
      notification: null
    }
  },
  watch: {
    message (val) {
      this.$refs.audio.load()
      this.$refs.audio.play()
      this.notification = new Notification(`来外卖啦`, {
        body: val
      })

      this.$notify({
        title: `来外卖啦`,
        message: val,
        duration: 0
      })
    }
  }
}
</script>
<template>
  <audio style="display:none;" ref="audio">
      <source :src="baseUrl + message" type="audio/mp3">
  </audio>
</template>
<style>

</style>



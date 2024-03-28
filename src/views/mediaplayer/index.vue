<template>
  <div class="app-container">
    <h2> media and video play and upload try table list play or upload play </h2>
  </div>
</template>

<script>

export default {
  name: 'MediaPlayerDemo',
  data() {
    return {
      activeName: 'directly',
      inputData: 'https://github.com/PanJiaChen/vue-element-admin'
    }
  },
  methods: {
    clipboardSuccess() {
      this.$message({
        message: 'Copy successfully',
        type: 'success',
        duration: 1500
      })
    }
  }
}
</script>


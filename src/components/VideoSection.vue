<template>
  <section class="video">
    <youtube
      :video-id="videoId"
      :player-width="width"
      :player-height="!isMobile ? height : heightMobile"
      :allowfullscreen="allowfullscreen"
    ></youtube>
  </section>
</template>

<script>
export default {
  name: 'Videos',
  data() {
    return {
      mobileBreakpoint: 1024,
      windowWidth: window.innerWidth,
      isMobile: false,
      videoId: 'Kfuga7eL-yE',
      width: '100%',
      height: 770,
      heightMobile: 400,
      allowfullscreen: 0
    }
  },
  props: {},
  created() {},
  methods: {
    toggleMobile() {
      if (window.innerWidth <= this.mobileBreakpoint) {
        this.isMobile = true
      } else {
        this.isMobile = false
      }
    },
  },
  mounted() {
    window.addEventListener('resize', this.toggleMobile)
    this.toggleMobile()
  },
  beforeDestroy() {
    window.removeEventListener('resize', this.toggleMobile)
    this.toggleMobile()
  },
}
</script>

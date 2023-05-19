<script>
export default {
  mounted () {
    document.addEventListener('visibilitychange', this.handleVisibility, false)
  },
  methods: {
    handleVisibility () {
      // eslint-disable-next-line no-empty
      if (document.visibilityState === 'hidden') {
        
      // eslint-disable-next-line no-empty
      } else {
        
      }
    }
  }
};
</script>
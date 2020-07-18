<template lang="pug">
  #app
    TheNavigationBar
    nuxt
</template>

<script>
import TheNavigationBar from '@/components/organisms/TheNavigationBar'

export default {
  components: {
    TheNavigationBar,
  },
}
</script>

<style lang="scss">
html {
  background-color: #fcfaff;
}

.container {
  margin: auto;
  padding: 16px;
}
</style>

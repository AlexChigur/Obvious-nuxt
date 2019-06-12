<template xmlns="http://www.w3.org/1999/html" lang="pug">

  .app
    base-header
    home-index

</template>

<script>
import BaseHeader from './BaseHeader/BaseHeader'
import HomeIndex from './HomeIndex'
// import HomeIndex from "../pages/HomeIndex";
// import BaseFooter from "../pages/BaseFooter/BaseFooter";
export default {
  name: 'App',
  components: { HomeIndex, BaseHeader },
  data () {
    return {

    }
  }
}
</script>

<style lang="sass">

  @import '../../node_modules/bootstrap/scss/functions'
  @import '../../node_modules/bootstrap/scss/variables'
  @import '../../node_modules/bootstrap/scss/mixins/breakpoints'
  @import url('https://fonts.googleapis.com/css?family=Montserrat:400,500,700&subset=cyrillic,cyrillic-ext,latin-ext,vietnamese')
  $font: Montserrat, Helvetica, sans-serif

  body
    margin: 0

</style>

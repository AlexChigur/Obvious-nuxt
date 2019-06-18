<template lang="pug">
  .home-index
    .advantages
      advantage-block
      home-steps
    .our-clients
      our-clients

</template>

<script>
import AdvantageBlock from './Home/AdvantageBlock'
import HomeSteps from '@/components/Home/HomeSteps/HomeSteps'
import OurClients from '@/components/OurClients'
export default {
  name: 'HomeIndex',
  components: { OurClients, HomeSteps, AdvantageBlock }
}
</script>

<style lang="sass" scoped>

  @import '../../node_modules/bootstrap/scss/functions'
  @import '../../node_modules/bootstrap/scss/variables'
  @import '../../node_modules/bootstrap/scss/mixins/breakpoints'
  @import url('https://fonts.googleapis.com/css?family=Montserrat:400,500,700&subset=cyrillic,cyrillic-ext,latin-ext,vietnamese')
  $font: Montserrat, Helvetica, sans-serif

  .advantages
    height: 100%
    background-image: linear-gradient(to bottom, #02343e, #001317)
    clip-path: polygon(50% 4%, 100% 0, 100% 95%, 50% 100%, 0% 95%, 0 0)
    +media-breakpoint-down(sm)
      clip-path: polygon(0 0, 100% 5%, 100% 100%, 0 100%)
    margin-top: 193px

</style>

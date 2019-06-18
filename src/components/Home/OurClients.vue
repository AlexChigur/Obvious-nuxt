<template lang="pug">

  .our-clients
    .our-clients-title
      | Ils nous font confiance
    .our-clients-list
      .our-clients-list__logo-item(v-for="image in firstImages")
        img(:src='image')
    .border-line
      .border-line__text
        | Notre partenaire
    .border-line__image
      img(src='~/assets/picture/client-images/logo-bpi-france.png')
    .poligon

</template>

<script>
import PictureElinor from '../../assets/picture/client-images/elinor-logo.png'
import PictureGroup from '../../assets/picture/client-images/group.svg'
import PictureHrMaps from '../../assets/picture/client-images/hrmaps-logo.png'
import PictureNexelec from '../../assets/picture/client-images/nexelec-logo.png'
import PictureNexeya from '../../assets/picture/client-images/nexeya-logo.png'
import PictureTC from '../../assets/picture/client-images/tc-logo.png'
import PictureKameleon from '../../assets/picture/client-images/logo-kameleon.png'
import PictureInvivox from '../../assets/picture/client-images/logo-invivox.png'
import PictureParticeep from '../../assets/picture/client-images/logo-particeep.png'

export default {
  name: 'OurClients',
  data () {
    return {
      firstImages: [
        PictureHrMaps,
        PictureElinor,
        PictureNexeya,
        PictureNexelec,
        PictureTC,
        PictureKameleon,
        PictureInvivox,
        PictureParticeep,
        PictureGroup
      ]
    }
  }
}
</script>

<style lang="sass" scoped>
  @import '../../../node_modules/bootstrap/scss/functions'
  @import '../../../node_modules/bootstrap/scss/variables'
  @import '../../../node_modules/bootstrap/scss/mixins/breakpoints'
  @import url('https://fonts.googleapis.com/css?family=Montserrat:400,500,700&subset=cyrillic,cyrillic-ext,latin-ext,vietnamese')
  $font: Montserrat, Helvetica, sans-serif

  .our-clients
    text-align: center
    font-family: $font
    display: flex
    flex-direction: column
    align-items: center
    width: 100%
    border-bottom: white solid 1px

  .our-clients-title
    font-size: 32px
    line-height: 1.41
    color: #383c3d
    margin-top: 112px
    margin-bottom: 64px

  .our-clients-list
    display: flex
    align-items: center
    justify-content: center
    flex-wrap: wrap

    &__logo-item
      padding: 0 64px 48px 64px
      img
        width: 100%
      +media-breakpoint-down(xs)
        width: 50%
        padding: 0 32px 22px 22px
        &:nth-child(2)
          width: 40%

  .border-line
    border-top: dotted 1.5px #7e7f80
    font-size: 24px
    line-height: 1.58
    width: 394px
    margin-top: 63px
    +media-breakpoint-down(sm)
      width: 272px
    &__text
      margin-top: 15.5px
    &__image
      margin-top: 40px
      align-items: center

</style>

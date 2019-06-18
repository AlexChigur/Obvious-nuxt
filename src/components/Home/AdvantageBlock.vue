<template lang="pug">

  .advantage-block
    .advantage-block-title
      | Pourquoi collaborer avec un partenaire ?
    .advantage-block-main
      .advantage-block-item(v-for="advantage in advantages")
        .advantage-block-item__logo
          img(:src="advantage.logo")
        .advantage-block-item__content
          .advantage-block-item__content__title {{ advantage.title }}
          .advantage-block-item__content__advantage {{ advantage.content}}
    .advantage-block-footer
      .advantage-block-footer__content
        | Comment s’y prendre ?
      .advantage-block-footer__logo
        img(src='~/assets/picture/scroll-down.svg')

</template>

<script>
import PictureCost from '~/assets/picture/cost-reduction.svg'
import PictureRisk from '~/assets/picture/risks.svg'
import PictureDevelopment from '~/assets/picture/development.svg'
import PictureInnovation from '~/assets/picture/innovation.svg'
export default {
  name: 'AdvantageBlock',
  data () {
    return {
      advantages: [
        {
          logo: PictureCost,
          title: 'Réduction des coûts',
          content: 'en partageant les coûts de développement'
        },
        {
          logo: PictureRisk,
          title: 'Partage des risques',
          content: 'financiers et techniques'
        },
        {
          logo: PictureDevelopment,
          title: 'Développement accéléré',
          content: 'en accédant à des ressources additionnelles des expertises complémentaires et de nouveaux marchés potentiels'
        },
        {
          logo: PictureInnovation,
          title: 'Financement dédié',
          content: 'À travers les programmes bilatéraux BPI France'
        }
      ]
    }
  }
}
</script>

<style lang="sass" scoped>
  @import '../../node_modules/bootstrap/scss/functions'
  @import '../../node_modules/bootstrap/scss/variables'
  @import '../../node_modules/bootstrap/scss/mixins/breakpoints'
  @import url('https://fonts.googleapis.com/css?family=Montserrat:400,500,700&subset=cyrillic,cyrillic-ext,latin-ext,vietnamese')
  $font: Montserrat, Helvetica, sans-serif
  @import url('https://fonts.googleapis.com/css?family=Montserrat:400,500,700&subset=cyrillic,cyrillic-ext,latin-ext,vietnamese')
  $font: Montserrat, Helvetica, sans-serif

  .advantage-block
    display: flex
    align-items: center
    flex-direction: column

  .advantage-block-title
    font-family: $font
    font-size: 32px
    color: #ffffff
    display: flex
    line-height: 1.41
    margin-top: 196px
    text-align: center
    +media-breakpoint-down(sm)
      width: 266px
      font-size: 24px

  .advantage-block-main
    display: flex
    flex-wrap: wrap
    justify-content: space-between
    width: 896px
    +media-breakpoint-down(md)
      justify-content: space-evenly
      flex-direction: column
      align-items: center

  .advantage-block-item
    display: flex
    font-family: $font
    font-size: 16px
    line-height: 1.63
    color: #009fc1
    font-weight: bold
    margin-top: 84px
    +media-breakpoint-down(sm)
      flex-direction: column
      align-items: center
    &__logo
      text-align: center
      width: 120px
      height: 119px
      margin-right: 24px
      +media-breakpoint-down(sm)
        margin: 32px 0 0 0
    &__content
      font-size: 16px
      font-family: $font
      +media-breakpoint-down(sm)
        text-align: center
      &__title
        font-weight: bold
        line-height: 1.63
        color: #009fc1
      &__advantage
        line-height: 1.5
        color: white
        font-weight: normal
        width: 269px

  .advantage-block-footer
    display: flex
    flex-direction: column
    align-items: center
    margin-top: 88px
    &__content
      font-family: $font
      font-size: 14px
      font-weight: bold
      letter-spacing: 1.2px
      text-align: center
      color: #009fc1

</style>

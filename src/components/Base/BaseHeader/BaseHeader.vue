<template lang="pug">

  .base-header.g-container
    .base-header-container
      .base-header-container__logo
        img(src="~/assets/logo.svg")
      a.base-header-container__button(href="#base-footer")
        .base-header-container__button__text
          | CONTACTEZ-NOUS
    .base-header-title
      | Booster votre projet innovant
      br
      | avec un partenaire
    .block-particles
      vue-particles(
      color='#009fc1'
      )

</template>

<script>
export default {
  name: 'BaseHeader'
}
</script>

<style lang="sass" scoped>
@import '../../../../node_modules/bootstrap/scss/functions'
@import '../../../../node_modules/bootstrap/scss/variables'
@import '../../../../node_modules/bootstrap/scss/mixins/breakpoints'
@import url('https://fonts.googleapis.com/css?family=Montserrat:400,500,700&subset=cyrillic,cyrillic-ext,latin-ext,vietnamese')
$font: Montserrat, Helvetica, sans-serif

.base-header
  text-align: center
  display: flex
  flex-direction: column
  align-items: center

.base-header-container
  margin-top: 32px
  display: flex
  align-items: center
  justify-content: space-between
  font-size: 18px
  font-weight: bold
  font-family: $font
  letter-spacing: 1.5px
  color: #ffffff
  width: 100%
  +media-breakpoint-down(sm)
    justify-content: space-around
  +media-breakpoint-down(xs)
    justify-content: space-between
  &__logo img
    +media-breakpoint-down(sm)
      width: 149px
    +media-breakpoint-down(xs)
      width: 150px
  &__button
    background-color: #009fc1
    border-radius: 2px
    width: 223px
    height: 48px
    display: flex
    align-items: center
    justify-content: center
    +media-breakpoint-down(sm)
      width: 149px
    cursor: pointer
    text-decoration: none
    +media-breakpoint-down(xs)
      width: 100px
    &__text
      color: #ffffff
      +media-breakpoint-down(sm)
        font-size: 12px
        letter-spacing: 1px

.base-header-title
  font-family: $font
  font-size: 48px
  font-weight: 600
  line-height: 1.33
  color: #009fc1
  width: 896px
  margin-top: 113px
  +media-breakpoint-down(md)
    max-width: 700px
  +media-breakpoint-down(sm)
    margin: 72px 24px 0 46px
    width: 250px
    text-align: left
    font-size: 28px

.block-particles
  width: 833px
  height: 607px
  position: absolute
  right: 0
  z-index: -1
  +media-breakpoint-down(sm)
    display: none

</style>

<template lang="pug">

  .item-step
    .item-step-accompaniment
      .item-step-main
        .item-border-step
        .item-border
          .item-border__number
            | ÉTAPE {{activeIndex + 1}}
          .item-border__arrow-previous(:class="{'inactive': activeIndex === 0}" @click="setStep(activeIndex - 1)")
            img(src="~/assets/picture/arrow-small-left.png")
          .item-border__arrow-next(:class="{'opacity': activeIndex >= stepsLength - 1}" @click="setStep(activeIndex + 1)")
            img(src='~/assets/picture/arrow-small.svg')
        .item-content
          .item-content__title {{step.title}}
          .item-content__point(v-for="item in step.message")
            img(src='~/assets/picture/bullet.svg')
            .point-text {{item}}
        .item-content-mediabreakpoint
          .item-content-border
          .item-content-resize(v-for="(titles, index) in stepTitle")
            .item-content-resize__title
              base-sphere(:index="index")
              .item-content-resize__title__main-title {{titles}}
            .item-content-resize__message(v-for="(item,text) in step.message")
              img(src='~/assets/picture/bullet.svg')
              .item-content-resize__message__text {{item}}

</template>

<script>
import BaseSphere from '@/components/Base/BaseSphere'
export default {
  name: 'ItemStep',
  components: { BaseSphere },
  props: {
    activeIndex: {
      type: Number,
      default: null
    },
    step: {
      type: Object,
      default () {
        return {}
      }
    },
    stepsLength: {
      type: Number,
      default: null
    },
    stepTitle: {
      type: Array,
      default () {
        return []
      }
    },
    nameSteps: {
      type: Array,
      default () {
        return []
      }
    }
  },
  data () {
    return {
      index: 1
    }
  },
  methods: {
    setStep (activeIndex) {
      this.$emit('setStep', activeIndex)
    }
  }
}
</script>

<style scoped lang="sass">
  @import '../../node_modules/bootstrap/scss/functions'
  @import '../../node_modules/bootstrap/scss/variables'
  @import '../../node_modules/bootstrap/scss/mixins/breakpoints'
  @import url('https://fonts.googleapis.com/css?family=Montserrat:400,500,700&subset=cyrillic,cyrillic-ext,latin-ext,vietnamese')
  $font: Montserrat, Helvetica, sans-serif

  img
    width: 24px
    height: 24px

  .opacity
    opacity: 0.3
    pointer-events: none

  .inactive
    pointer-events: none

  .item-step-accompaniment
    display: flex
    align-items: flex-start

  .item-border
    display: flex
    align-items: center
    border: 1px #009fc1
    border-style: none none solid none
    width: 436px
    justify-content: space-between
    margin-top: 68px
    font-family: $font
    font-size: 12px
    font-weight: bold
    +media-breakpoint-down(sm)
      display: none
    &__number
      color: #009fc1
      display: flex
      align-items: center
    &__arrow-previous
      display: flex
      align-items: center
      margin-left: 334px
      width: 24px
      height: 24px
      cursor: pointer
    &__arrow-next
      width: 24px
      height: 24px
      cursor: pointer

  .item-content
    display: flex
    flex-direction: column
    margin-top: 16px
    font-family: $font
    font-size: 24px
    line-height: 1.58
    color: white
    width: 436px
    text-align: left
    +media-breakpoint-down(sm)
      display: none
    &__point
      display: flex
      font-size: 16px
      line-height: 1.5
      margin-top: 16px
      align-items: flex-start
  .item-content-mediabreakpoint
    position: relative
    +media-breakpoint-up(md)
      display: none

  .item-content-border
    top: 50px
    left: 12px
    position: absolute
    border-left: 1px dotted
    border-image: linear-gradient(to bottom, transparent, white, transparent) 1 50%;
    height: 1000px
    z-index: -1

  .item-content-resize
    font-family: $font
    display: flex
    flex-direction: column
    color: white
    line-height: 1.5
    &__title
      display: flex
      margin-top: 48px
      &__main-title
        margin-left: 16px
        font-weight: bold
    &__message
      display: flex
      flex-direction: row
      margin-top: 16px
      &__text
        margin-left: 16px

</style>

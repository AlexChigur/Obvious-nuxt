<template lang="pug">
  div
    .sphere(:class="[{'active': isActive(index)},`sphere--${index + 1}`]")
      .number {{index + 1}}
        .text {{item}}
</template>

<script>
export default {
  name: 'BaseSphere',
  props: {
    item: {
      type: String,
      default: ''
    },
    index: {
      type: Number,
      default: null
    },
    activeIndex: {
      type: Number,
      default: null
    }
  },
  methods: {
    isActive (index) {
      return this.activeIndex !== null
        ? index <= this.activeIndex
        : true
    }
  }
}
</script>

<style scoped lang="sass">
.sphere
  color: white
  display: flex
  align-items: center
  justify-content: center
  width: 24px
  height: 24px
  opacity: .6
  box-shadow: 0 0 8px 0 #7e7f80
  border: solid 1px #7e7f80
  border-radius: 100px
  background: linear-gradient(143deg, #383c3d, #9ea4a5)
  font-size: 12px
  font-family: $noto-sans
  font-weight: bold
  &--1
    bottom: 106px
    left: 150px
  &--2
    flex-direction: column
    left: 78px
    bottom: 1px
    .text
      left: -60px
      top: 30px
  &--3
    bottom: 250px
    left: 30px

.number
  position: relative
  display: flex

.text
  position: absolute
  font-family: $font-family-sans-serif
  font-weight: bold
  font-size: 13px
  width: 132px
  top: 0
  left: 30px

.active
  box-shadow: 0 0 8px 0 #009fc1
  border: solid 1px #009fc1
  background: linear-gradient(143deg, #383c3d, #009fc1)
  font-size: 12px
  opacity: unset
</style>

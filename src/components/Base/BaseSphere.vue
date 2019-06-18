<template lang="pug">
  div
    .sphere(:class="[{'active': isActive(index)},`sphere--${index + 1}`]" @click="setStep(activeIndex + 1); previousStep")
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
    },
    setStep (activeIndex) {
      this.$emit('setStep', activeIndex)
    },
    previousStep () {
      if (this.index <= this.activeIndex) { return this.activeIndex - 1 }
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
  font-weight: bold
  cursor: pointer

.number
  position: relative
  display: flex
  font-family: $noto-sans

.text
  position: absolute
  font-family: $font-family-sans-serif
  font-weight: bold
  font-size: 13px
  width: 132px
  line-height: 1.31
  top: 0
  left: 22px

.active
  box-shadow: 0 0 8px 0 #009fc1
  border: solid 1px #009fc1
  background: linear-gradient(143deg, #383c3d, #009fc1)
  font-size: 12px
  opacity: unset
  pointer-events: none
</style>

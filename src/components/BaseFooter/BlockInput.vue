<template lang="pug">

  .block-input
    .block-input__name(v-if="hasFocus") {{label}}
    input.block-input__data(
    :class="{'active': hasFocus}"
    v-model="inputValue"
    v-bind="{...$attrs}"
    @focus="hasFocus = true"
    @blur="hasFocus = false"
    )

</template>

<script>
    export default {
        data () {
          return {
            hasFocus: false,
          }
        },
        name: "BlockInput",
        props: {
          label: {
            type: String,
            default: ''
          },
          value: {
            type: String,
            default: ''
          }
        },
      computed: {
          inputValue: {
            get () {
              return this.value
            },
            set (value) {
              this.$emit('input', value)
            }
          },
        }
      }
</script>

<style lang="sass" scoped>
  @import url('https://fonts.googleapis.com/css?family=Montserrat:400,500,700&subset=cyrillic,cyrillic-ext,latin-ext,vietnamese')
  $font: Montserrat, Helvetica, sans-serif

  ::placeholder
    color: white
    opacity: 0.2
    font-family: $font

  .block-input
    font-family: $font
    position: relative
    &__name
      position: absolute
      color: #009fc1
      font-size: 11px
      font-weight: bold
    &__data
      margin-top: 9px
      background-color: transparent
      border: none
      height: 40px
      border-bottom: solid 1px gray
      &:focus::placeholder
        color: transparent
      width: 344px
      outline: none
      color: white

  .active
    border-color: #009fc1




</style>

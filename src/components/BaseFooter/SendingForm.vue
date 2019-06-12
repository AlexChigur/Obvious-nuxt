<template lang="pug">

  .sending-form
    .sending-form__title
      | Discutons de votre projet
    .sending-form__content
      | Nous reviendrons vers vous dans les prochaines 24h.
    .block-input
      block-input(
      label="Votre nom"
      v-model="form.name"
      placeholder="Name"
      )
      block-input(
      label="Votre email"
      v-model="form.email"
      placeholder="email"
      )
      text-area(
      label="Votre message"
      v-model="form.message"
      placeholder="Message"
      )
    .sending-checkbox
      .sending-checkbox__custom(@click="Check")
        .sending-checkbox__custom__checked(v-if='checked')
          | &#10004
      .sending-checkbox__agreement
        | J’accepte la
        a.sending-checkbox__agreement__email(href='') Politique de confidentialité
    .sending-button
      .sending-button__indent(
      :class="{'active' : validForm}"
      @click="successSend"
      :disabled="disabledButton"
      )
        .sending-button__indent__text
          | Envoyer ma demande
        .sending-button__indent__arrow
          img(src='../../../assets/arrow-small.svg')

</template>

<script>
    const emailCheckRegex = /^(([^<>()\[\]\\.,;:\s@"]+(\.[^<>()\[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/
    const nameCheckRegex = /[a-zA-Z-\s]/
    import BlockInput from "./BlockInput";
    import TextArea from "@/components/Base/BaseFooter/TextArea";
    export default {
      name: "SendingForm",
      data() {
        return {
          disabledButton: true,
          hasFocus: true,
          checked: false,
          form: {
            name: '',
            email: '',
            message: '',
          }
        }
      },
      components: {TextArea, BlockInput},
      computed: {
        isValidEmail () {
          return emailCheckRegex.test(this.form.email)
        },
        isValidName () {
          return nameCheckRegex.test(this.form.name)
        },
        validForm () {
          if (this.isValidEmail && this.checked && this.isValidName && this.form.message) {
            return true
          }
        }
      },
      methods: {
        Check () {
          this.checked = !this.checked
        },
        successSend () {
          this.$emit('successSend')
      }

      }
    }
</script>

<style lang="sass" scoped>
  @import url('https://fonts.googleapis.com/css?family=Montserrat:400,500,700&subset=cyrillic,cyrillic-ext,latin-ext,vietnamese')
  $font: Montserrat, Helvetica, sans-serif

  ::placeholder
    color: white
    opacity: 0.6

  .sending-form
    color: white
    margin: 224px 0 0 241px
    font-family: $font
    &__title
      width: 404px
      font-size: 32px
      line-height: 1.31
    &__content
      width: 340px
      font-size: 16px
      line-height: 1.5
      margin-top: 8px

  .block-input
    margin-top: 32px

  .sending-checkbox
    display: flex
    align-items: center
    font-size: 12px
    color: white
    margin-top: 33px
    &__custom
      text-align: center
      width: 18px
      height: 18px
      border: solid 1px
      cursor: pointer
    &__agreement
      margin-left: 7px
      &__email
        text-decoration: none
        color: #009fc1
        border-bottom: dotted 1px
        margin-left: 1px

  .sending-button
    margin-top: 34px
    width: 344px
    height: 56px
    border: dotted 2px gray
    border-radius: 4px
    cursor: default
    font-size: 12px
    letter-spacing: 1px
    font-weight: bold
    &__indent
      opacity: 0.2
      border-radius: 4px
      margin: 4px auto
      display: flex
      align-items: center
      justify-content: flex-start
      width: 336px
      height: 48px
      background-color: gray
      &__text
        margin-left: 32px
      &__arrow
        margin-left: 10px

  .active
    background-color: #009fc1
    opacity: 1
    cursor: pointer
    box-shadow: 0 0 8px 0 #009fc1




</style>

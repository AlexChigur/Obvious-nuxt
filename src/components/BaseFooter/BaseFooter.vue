<template lang="pug">

  .base-footer#base-footer
    .footer-content
      .block-footer
        footer-contacts
      .sending-form
        sending-form(
        @successSend="successSend"
        v-if="!sendMessage"
        )
      .successfully-sent
        successfully-sent(
        @successSend="successSend"
        v-if="sendMessage"
        )
    .block-company
      .block-company-group
        .block-company-group__consalting
          | Ob’vious Consulting fait partie du groupe Ob'vious
        .block-company-group__consalting__confidentiality
          a.block-company-group__consalting__confidentiality__text(href='') Politique de confidentialité
      .block-company-portal
        .block-company-portal__obvious
          | Portail Ob’vious
          .block-company-portal__obvious__image
            img(src="../../../assets/contacts-images/new-tab.svg")
        .block-company-portal__year
          | © Ob-vious — 2019

</template>

<script>
    import SendingForm from "@/components/Base/BaseFooter/SendingForm";
    import FooterContacts from "@/components/Base/BaseFooter/FooterContacts";
    import SuccessfullySent from "@/components/Base/BaseFooter/SuccessfullySent";
    export default {
      data () {
        return {
          sendMessage: false
        }
      },
      name: "BaseFooter",
      components: {SuccessfullySent, FooterContacts, SendingForm},
      methods: {
        successSend () {
          this.sendMessage = !this.sendMessage
        }
      }
    }
</script>

<style lang="sass" scoped>
  @import url('https://fonts.googleapis.com/css?family=Montserrat:400,500,700&subset=cyrillic,cyrillic-ext,latin-ext,vietnamese')
  $font: Montserrat, Helvetica, sans-serif

  .base-footer
    background-image: linear-gradient(to bottom, #02343e, #001317)
    clip-path: polygon(50% 15%, 100% 0, 100% 100%, 50% 100%, 0 100%, 0 0)
    height: 100%

  .footer-content
    display: flex
    margin-left: 192px

  .block-company
    font-family: $font
    font-size: 16px
    color: white

  .block-company-group
    display: flex
    justify-content: space-between
    margin: 128px 192px 0 192px
    &__consalting
      &__confidentiality
        &__text
          text-decoration: none
          color: #009fc1

  .block-company-portal
    display: flex
    justify-content: space-between
    margin: 0 192px 0 192px
    align-items: center
    color: #009fc1
    &__obvious
      display: flex
      align-items: center
      font-weight: bold
    &__year
      color: white



</style>

<template lang="pug">

    .footer-contacts
      .footer-contacts__title
        | Contactez-nous
      .main-contact-information(v-for="contact in contacts")
        .contact-image
          img(:src="contact.image")
        .contact-data
          .contact-data__name {{contact.name}}
          .contact-data__post {{contact.post}}
          a.contact-data__email(href="aurelien@ob-vious.com") {{contact.email}}
          .contact-data__shape
            img(:src="contact.shape")

</template>

<script>
    import ImageAurelien from '../../../assets/contacts-images/aurelien.png'
    import ImageYannick from '../../../assets/contacts-images/yannick.png'
    import PictureShape from '../../../assets/contacts-images/combined-shape.svg'
    export default {
        name: "FooterContacts",
      data () {
        return {
          contacts: [
            {
              image: ImageAurelien,
              name: 'Aurélien Romain',
              post: 'Consultant',
              email: 'aurelien@ob-vious.com',
              shape: PictureShape

            },
            {
              image: ImageYannick,
              name: 'Yannick Tranchier',
              post: 'CEO',
              email: 'yannick@ob-vious.com',
              shape: PictureShape
            }
          ]


        }
      }
    }
</script>

<style lang="sass" scoped>
  @import url('https://fonts.googleapis.com/css?family=Montserrat:400,500,700&subset=cyrillic,cyrillic-ext,latin-ext,vietnamese')
  $font: Montserrat, Helvetica, sans-serif

  .footer-contacts
    margin-top: 224px
    width: 381px
    font-family: $font
    color: white
    &__title
      font-size: 32px

  .main-contact-information
    display: flex
    margin-top: 40px

  .contact-data
    display: flex
    flex-direction: column
    margin-left: 24px
    &__name
      margin-top: 12px
      line-height: 1.5
      font-size: 16px
    &__post
      margin-top: 4px
      font-size: 12px
      font-weight: bold
    &__email
      margin-top: 12px
      font-size: 12px
      font-weight: bold
      color: #009fc1
      text-decoration: none
    &__shape
      margin-top: 16px


</style>

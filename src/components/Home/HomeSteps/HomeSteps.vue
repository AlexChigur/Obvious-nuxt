<template lang="pug">

  .home-steps
    .home-title
      | Nous vous accompagnons lors des 3 étapes clés :
    .block-steps
      .block-steps__list
        item-step(
          :step="steps[activeIndex]"
          @setStep="setStep"
          :activeIndex="activeIndex"
          :stepsLength="steps.length"
          :stepTitle="titles"
          :nameSteps="nameSteps"
          )
      .block-steps__vortex
        vortex(
          :activeIndex="activeIndex"
          :nameSteps="nameSteps"
          )
    .block-finance
      .block-finance__logo
        img(src="~/assets/picture/plus.svg")
      .block-finance__title {{finance.title}}
      .block-finance__content {{finance.content}}
        .block-finance__content__list(v-for="item in finance.list")
          .block-finance__content__list__bullet
            img(src='~/assets/picture/bullet.svg')
          .block-finance__content__list__text {{item}}

</template>

<script>

import ItemStep from '@/components/ItemStep'
import Vortex from '@/components/Vortex'
export default {
  name: 'HomeSteps',
  components: { Vortex, ItemStep },
  data () {
    return {
      activeIndex: 0,
      stepsLength: 0,
      steps: [
        {
          title: 'Analyse et initialisation de la collaboration',
          message:
                [
                  'Analyse et définition des besoins: positionnement stratégique, périmètre fonctionnel, choix technologique',
                  'Accompagnement dans la recherche du partenaire idéal en Russie',
                  'Aide à la sélection du partenaire'
                ]
        },
        {
          title: 'Co-développement',
          message:
                [
                  'Négociation et contractualisation avec le partenaire (chiffrage, propriété intellectuelle, et assistance juridique)',
                  'Lancement et suivi du projet: méthodologie et support pour les équipes, reporting consolidé'
                ]
        },
        {
          title: 'Déploiement commercial',
          message:
                [
                  'Sélection d’un intégrateur / distributeur',
                  'Montage d’un accord commercial (JV, filiale, autre)',
                  'Financement et investissement'
                ]
        }
      ],
      finance: {
        title: 'Financement du projet collaboratif',
        content: 'Tout au long du projet, nous montons les dossiers permettant de financer le projet collaboratif',
        list: [
          'Aide au Partenariat Technologique',
          'Aide pour le Développement de l’Innovation en Collaboration Internationale',
          'Assurance Prospection',
          'Prêt pour l’export et l’internationalisation'
        ]
      },
      nameSteps: ['Analyse', 'Co-développement', 'Déploiement']
    }
  },
  computed: {
    titles () {
      return this.steps.map(step => {
        return step.title
      })
    }
  },
  methods: {
    setStep (activeIndex) {
      this.activeIndex = activeIndex
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

  .block-steps-resize
    font-size: 20px
    color: white

  .home-steps
    margin: 0 192px 0 192px

  .home-title
    text-align: center
    font-family: $font
    font-size: 32px
    line-height: 1.41
    color: #ffffff
    margin-top: 88px
    +media-breakpoint-down(sm)
      width: 266px

  .block-steps
    display: flex
    justify-content: space-between
    +media-breakpoint-down(md)
      flex-direction: column
      align-items: center
    &__vortex
      margin: 80px 0 0 0
      +media-breakpoint-down(sm)
        display: none

  .block-finance
    margin: 0 0 208px 0
    display: flex
    flex-direction: column
    font-family: $font
    font-size: 16px
    width: 436px
    color: white
    line-height: 1.5
    +media-breakpoint-down(sm)
    &__logo
      margin-top: 116px
    &__title
      font-weight: bold
      color: #009fc1
      line-height: 1.63
      margin-top: 24px
    +media-breakpoint-down(sm)
      width: 272px
      text-align: center
    &__content
      margin-top: 16px
      color: white
      font-weight: normal
      &__list
        display: flex
        flex-direction: row
        margin-top: 16px
        +media-breakpoint-down(sm)
          justify-content: flex-start
        &__bullet
          width: 24px
          height: 24px
        &__text
          margin-left: 12px
        +media-breakpoint-down(sm)
          text-align: left
          width: 247px

</style>

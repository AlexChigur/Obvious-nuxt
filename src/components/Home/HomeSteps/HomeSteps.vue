<template lang="pug">

  .home-steps.g-container
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
          @setStep="setStep"
          @previousStep="previousStep"
          )
    .block-finance.g-container
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

import ItemStep from '@/components/Home/HomeSteps/ItemStep'
import Vortex from '@/components/Home/HomeSteps/Vortex'
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
@import '../../../../node_modules/bootstrap/scss/functions'
@import '../../../../node_modules/bootstrap/scss/variables'
@import '../../../../node_modules/bootstrap/scss/mixins/breakpoints'
@import url('https://fonts.googleapis.com/css?family=Montserrat:400,500,700&subset=cyrillic,cyrillic-ext,latin-ext,vietnamese')
$font: Montserrat, Helvetica, sans-serif

.block-steps-resize
  font-size: 20px
  color: white

.home-title
  text-align: center
  font-family: $font
  font-size: 32px
  line-height: 1.41
  color: #ffffff
  margin-top: 88px
  +media-breakpoint-down(xs)
    font-size: 24px
    margin-top: 80px

.block-steps
  display: flex
  +media-breakpoint-down(md)
    flex-direction: column
    align-items: center
  &__vortex
    margin: 80px 0 0 156px
    +media-breakpoint-down(md)
      margin: 100px
    +media-breakpoint-down(sm)
      display: none

.block-finance
  display: flex
  flex-direction: column
  font-family: $font
  font-size: 16px
  color: white
  line-height: 1.5
  margin-bottom: 132px
  +media-breakpoint-down(md)
    align-items: center
    justify-items: center
    width: 272px
  +media-breakpoint-down(xs)
    text-align: center
    margin-bottom: 75px
  &__logo
    margin-top: 84px
    +media-breakpoint-down(xs)
      margin-top: 48px

  &__title
    font-weight: bold
    color: #009fc1
    line-height: 1.63
    margin-top: 24px
    +media-breakpoint-down(lg)
      width: 436px
      text-align: left
    +media-breakpoint-down(sm)
      text-align: center
      width: 272px

  &__content
    width: 436px
    margin: 4px 0 16px 0
    color: white
    font-weight: normal
    +media-breakpoint-down(sm)
      text-align: center
      width: 272px
      margin: 16px 0 24px 0

    &__list
      width: 416px
      display: flex
      flex-direction: row
      margin-bottom: 12px
      +media-breakpoint-down(sm)
        justify-content: flex-start
        margin-right: 4px
        width: 272px

      &__bullet
        width: 24px
        height: 24px
        transform: translateX(-8px)
      +media-breakpoint-down(sm)
        text-align: left

</style>

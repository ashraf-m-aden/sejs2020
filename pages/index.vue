<template>
  <!-- eslint-disable max-len -->
  <div class="container-fluid">
    <Carousel></Carousel>
    <div class="container border-bottom mb-5"></div>
    <Mot class="container"></Mot>
    <div class="container border-bottom mb-5 mt-5"></div>
    <div class="city">
      <Carte class="container"></Carte>
    </div>

    <div class="container border-bottom mb-5 mt-5"></div>
    <div class="row">
      <div class="col-12 col-md-4">
        <Populaires></Populaires>
      </div>
      <div class="col-12 col-md-8">
        <NewMenu></NewMenu>
      </div>
    </div>
  </div>
</template>

<script>
import NewMenu from '~/pages/news/NewMenu.vue'
import Carousel from '~/components/Carousel.vue'
import Mot from '~/components/MotduMinistre.vue'
import Carte from '~/components/GrandeCarte.vue'
import Populaires from '~/components/Populaires.vue'
export default {
  components: {
    NewMenu,
    Carousel,
    Mot,
    Carte,
    Populaires,
  },
  head() {
    return {
      title: "Secretariat d'Etat à la Jeunesse et aux Sports",
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: "Le Secretariat d'Etat à la Jeunesse et aux Sports",
        },
      ],
    }
  },
}
</script>

<style lang="css" scoped>
.land {
  fill: #cccccc;
  fill-opacity: 1;
  stroke: white;
  stroke-opacity: 1;
  stroke-width: 0.5;
}
#svg {
  background-repeat: repeat;
  background-size: cover;
}
.city {
  border-top: #0b7dff 2px solid;
  border-bottom: #38ca0b 2px solid;
  border-radius: 50px;
}
</style>

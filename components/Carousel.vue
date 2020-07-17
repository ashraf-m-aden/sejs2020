<template>
  <div class="row">
    <div class="col-12">
      <div class="jumbotron bg-light text-center">
        <b-carousel
          id="carousel-1"
          v-model="slide"
          class="mr-auto ml-auto"
          :interval="4000"
          controls
          indicators
          background="#ababab"
          style="text-shadow: 1px 1px 2px #333;"
          @sliding-start="onSlideStart"
          @sliding-end="onSlideEnd"
        >
          <!-- Slides with custom text -->
          <b-carousel-slide
            class="carousel img-fluid"
            img-height="500px"
            img-src="~/assets/banner1.jpg"
          >
          </b-carousel-slide>

          <!-- Slides with image only -->
          <b-carousel-slide
            class="carousel img-fluid"
            img-src="~/assets/banner2.jpg"
          ></b-carousel-slide>

          <!-- Slides with img slot -->
          <!-- Note the classes .d-block and .img-fluid to prevent browser default image alignment -->
          <b-carousel-slide class="carousel img-fluid">
            <template v-slot:img>
              <img
                class="d-block img-fluid w-100"
                src="~/assets/banner3.jpg"
                alt="image slot"
              />
            </template>
          </b-carousel-slide>
        </b-carousel>
        <span class="display-4">
          Secretariat d'Etat à la Jeunesse et aux Sports
        </span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      slide: 0,
      sliding: null,
    }
  },
  methods: {
    onSlideStart(slide) {
      this.sliding = true
    },
    onSlideEnd(slide) {
      this.sliding = false
    },
  },
}
</script>

<style lang="css" scoped>
.carousel {
  width: 100%;
  background-size: cover;
}
@media (min-width: 1000px) {
  .carousel {
    width: 848px;
    height: 500px;
    background-size: cover;
  }
}
</style>

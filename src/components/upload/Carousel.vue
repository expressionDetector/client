<template>
  <div>
    <b-carousel
      id="carousel-1"
      :interval="2000"
      fade
      background="#ababab"
      img-width="800"
      img-height="100"
      style="text-shadow: 1px 1px 2px #333;"
      no-hover-pause
    >
      <b-carousel-slide img-src="https://picsum.photos/2040/1080/?random=52" class="carousel-image"></b-carousel-slide>
      <b-carousel-slide img-src="https://picsum.photos/2040/1080/?random=54" class="carousel-image"></b-carousel-slide>
      <b-carousel-slide img-src="https://picsum.photos/2040/1080/?random=58" class="carousel-image"></b-carousel-slide>
      <b-carousel-slide img-src="https://picsum.photos/2040/1080/?random=55" class="carousel-image"></b-carousel-slide>
    </b-carousel>
  </div>
</template>

<script>
export default {
  name: "Carousel"
};
</script>

<style scoped>
.carousel-image {
  height: 100vh !important;
}
</style>
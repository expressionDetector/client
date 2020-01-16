<template>
  <div>
    <b-carousel
      id="carousel-1"
      :interval="200"
      fade
      background="#ababab"
      img-width="800"
      img-height="100"
      style="text-shadow: 1px 1px 2px #333;"
    >
      <b-carousel-slide img-src="https://picsum.photos/800/600/?image=52" class="carousel-image"></b-carousel-slide>
      <b-carousel-slide img-src="https://picsum.photos/800/600/?image=54" class="carousel-image"></b-carousel-slide>
      <b-carousel-slide img-src="https://picsum.photos/800/600/?image=58" class="carousel-image"></b-carousel-slide>
      <b-carousel-slide img-src="https://picsum.photos/800/600/?image=55" class="carousel-image"></b-carousel-slide>
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
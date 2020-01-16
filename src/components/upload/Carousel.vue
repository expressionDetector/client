<template>
  <b-carousel
    id="carousel-1"
    :interval="3000"
    fade
    background="#ababab"
    img-width="800"
    img-height="100"
    style="text-shadow: 1px 1px 2px #333; "
  >
    <b-carousel-slide
      img-src="https://picsum.photos/800/600/?image=52"
      style="height:100vh !important"
    ></b-carousel-slide>
    <b-carousel-slide
      img-src="https://picsum.photos/800/600/?image=54"
      style="height:100vh !important"
    ></b-carousel-slide>
    <b-carousel-slide
      img-src="https://picsum.photos/800/600/?image=58"
      style="height:100vh !important"
    ></b-carousel-slide>
    <b-carousel-slide
      img-src="https://picsum.photos/800/600/?image=55"
      style="height:100vh !important"
    ></b-carousel-slide>
    <UploadForm></UploadForm>
  </b-carousel>
</template>

<script>
import UploadForm from "./Form";
export default {
  name: "Carousel",
  data() {
    return {};
  },
  components: {
    UploadForm
  },
  methods: {},
  created() {}
};
</script>

<style scoped>
</style>
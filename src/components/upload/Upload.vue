<template>
  <div>
    <Carousel></Carousel>
    <UploadForm @catchUrl='catchUrl' />
  </div>
</template>

<script>
import axios from "axios";
import Carousel from "./Carousel";
import UploadForm from "./Form"
export default {
  name: "Upload",
  data() {
    return {};
  },
  components: {
    Carousel,
    UploadForm
  },
  name: "Upload",
  methods: {
    catchUrl(url){
      this.$emit('url', url)
    }
  },
  created() {}
};
</script>
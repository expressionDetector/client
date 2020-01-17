<template>
  <div class="middle">
    <div class="d-flex flex-column justify-content-center container" v-if="url">
      <div class="justify-content-center">
        <img :src="url" class="image" />
      </div>

      <b-button
        @click="removeImage()"
        class="my-5 w-25 font-weight-bold"
        style="margin: 0 auto; font-size: large;"
      >Remove image</b-button>
    </div>

    <b-form-file
      v-model="file"
      @change="onFileChange"
      :state="Boolean(file)"
      placeholder="Choose a file or drop it here..."
      drop-placeholder="Drop file here..."
      action="/upload-single"
      method="post"
      enctype="multipart/form-data"
    ></b-form-file>

    <b-button
      class="mt-5 font-weight-bold"
      style="font-size: large;"
      v-if="file"
      @click="upload"
    >Upload</b-button>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "UploadForm",
  data() {
    return {
      file: null,
      url: null
    };
  },
  methods: {
    onFileChange(e) {
      const file = e.target.files[0];
      this.url = URL.createObjectURL(file);
    },
    removeImage: function() {
      this.file = null;
      this.url = null;
    },
    upload() {
      const fd = new FormData();
      fd.append("file", this.file);
      console.log(fd);
      axios({
        method: "post",
        url: "http://35.224.51.213:3000/image/singleupload",
        data: fd
      })
        .then(({ data }) => {
          this.$emit("catchUrl", data);
        })
        .catch(err => {
          console.log(err);
        });
    }
  },
  created() {}
};
</script>

<style scoped>
.middle {
  transition: 0.5s ease;
  position: absolute;
  background-color: rgba(82, 144, 210, 0.685);
  width: 80%;
  padding: 5vh;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  -ms-transform: translate(-50%, -50%);
  text-align: center;
  z-index: 999;
}
.image {
  height: 50vh;
  width: 50vh;
}
</style>
<template>
  <div class="middle">
    <div class="d-flex flex-column justify-content-center" v-if="url">
      <img :src="url" class="image" />
      <button @click="removeImage()">Remove image</button>
    </div>
    <b-form-file
      v-model="file"
      @change="onFileChange"
      :state="Boolean(file)"
      placeholder="Choose a file or drop it here..."
      drop-placeholder="Drop file here..."
    ></b-form-file>
    <b-button v-if="file" @click="upload">Upload</b-button>
  </div>
</template>

<script>
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
  height: 10vh;
  width: 10vh;
}
</style>
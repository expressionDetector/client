<template>
  <b-navbar toggleable="lg" type="dark" variant="info" style="position: sticky-top ; z-index:999">
    <b-navbar-brand href="#" @click='toUpload'>Expression Detection</b-navbar-brand>
    <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>
    <b-collapse id="nav-collapse" is-nav>
      <b-navbar-nav class="menu">
        <b-nav-item href="#" class="text-center" @click='toUpload'>Upload</b-nav-item>
      </b-navbar-nav>
    </b-collapse>
  </b-navbar>
</template>

<script>
export default {
  name: "Navigation",
  methods: {
    toUpload(){
      this.$emit('toUpload')
    }
  }
};
</script>

<style scoped>
@media (min-width: 576px) {
  .menu {
    width: 100%;
  }
}
@media (min-width: 768px) {
  .menu {
    width: 100%;
  }
}
@media (min-width: 992px) {
}
@media (min-width: 1200px) {
}
</style>
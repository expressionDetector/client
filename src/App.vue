<template>
    <div>
        <Parent></Parent>
        <input type="text" v-model='imageUrl'>
        <button @click='share'>Share</button>
    </div>
</template>

<script>
import Parent from "./components/Parent";
import axios from 'axios'
export default {
    data(){
        return {
          imageUrl: ''
        }
    },
    components: {
        Parent
    },
    methods: {
      share(){
        axios({
          method: 'POST',
          url: 'http://localhost:3000/share',
          data: {
            imageUrl: this.imageUrl
          }
        })
        .then(({data}) => {
          console.log(`Success`)
        })
        .catch((err) => {
          console.log(err)
        })
      }
    }
}
</script>

<style scoped>

</style>

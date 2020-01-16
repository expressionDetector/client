<template>
    <div>
        <Card />
        <Share @share='share' />
        <b-btn @click="detectImage">Show</b-btn>
    </div>
</template>
<script>
import axios from 'axios'
import Share from './Share'
import Card from './Card'
export default {
    data(){
        return{
        }
    },
    components: {
        Share,
        Card
    },
    props: ['imageUrl', 'apiUrl'],
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
        },
        detectImage(url){
            url = this.imageUrl
            console.log(url)
            axios.post(`${this.apiUrl}/image/detection`, {
                url
            })
            .then(({data}) => {
                console.log(data)
            })
            .catch(err => {
                console.log(err)
            })
        }
    },
    watch: {
        imageUrl: function (val) {  
            if(val){
                this.detectImage(val)
            }
        }
    }
}
</script>
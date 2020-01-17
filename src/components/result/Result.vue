<template>
    <div>
        <div class="container mt-5">
            <Card :results = "results" :imageUrl= "imageUrl" @share='share' :status='status' :message='message'/>
        </div>
    </div>
</template>
<script>
import axios from 'axios'
import Share from './Share'
import Card from './Card'
export default {
    data(){
        return{
            results: {},
            status: '',
            message: ''
        }
    },
    components: {
        Share,
        Card
    },
    props: ['imageUrl', 'apiUrl'],
    methods: {
        share(){
            this.status = 'loading'
            axios({
                method: 'POST',
                url: 'http://35.224.51.213:3000/share',
                data: {
                    imageUrl: this.imageUrl
                }
            })
            .then(({data}) => {
                this.status = 'success'
                window.open('https://www.pinterest.com/carlhermawan/expression-detector/', '_blank')
            })
            .catch((err) => {
                this.status = 'failed'
                this.message = err.response.status + ' ' + err.response.data.message
            })
        },
        detectImage(url){
            console.log(url)
            let self = this
            axios.post(`${this.apiUrl}/image/detection`, {
                url
            })
            .then(({data}) => {
                const detected = data.detected
                self.results = {
                    Joy: self.convertToNum(detected.joyLikelihood),
                    Sorrow: self.convertToNum(detected.sorrowLikelihood),
                    Anger: self.convertToNum(detected.angerLikelihood),
                    Surprise: self.convertToNum(detected.surpriseLikelihood),
                    Exposed: self.convertToNum(detected.underExposedLikelihood),
                    Blurred: self.convertToNum(detected.blurredLikelihood),
                    Headwear: self.convertToNum(detected.headwearLikelihood)
                }
            })
            .catch(err => {
                console.log(err)
            })
        },
        convertToNum(level){
            switch (level) {
                case 'VERY_UNLIKELY':
                    return 20
                case 'UNLIKELY':
                    return 40
                case 'LIKELY':
                    return 70
                case 'VERY_LIKELY':
                    return 100
                default:
                    return 50
            }
        }
    },
    mounted(){
        if(this.imageUrl){
            this.detectImage(this.imageUrl)
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
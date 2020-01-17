<template>
    <div>
        <Navigation @toUpload='toUpload' />
        <template v-if="isUpload">
            <Upload @url='catchUrl' />
        </template>
        <template v-else>
            <Result :imageUrl = "imageUrl" :apiUrl = "apiUrl" />
        </template>

    </div>
</template>
<script>
    import Navigation from "./general/Nav.vue";
    import Upload from "./upload/Upload";
    import Result from './result/Result'
    export default{
        data(){
            return {
                isUpload: true,
                imageUrl: '',
                apiUrl: 'http://35.224.51.213:3000'
            }
        },
        components: {
            Navigation,
            Upload,
            Result
        },
        methods: {
            toUpload(){
                this.isUpload = true
                this.imageUrl = null
            },
            catchUrl(payload){
                this.isUpload = false
                this.imageUrl = payload
            }
        },
        created(){

        }
    }
</script>
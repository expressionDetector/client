<template>
    <div>
        <Navigation />
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
                isUpload: false,
                imageUrl: 'https://cdn.psychologytoday.com/sites/default/files/styles/article-inline-half-caption/public/field_blog_entry_images/2018-09/shutterstock_648907024.jpg?itok=0hb44OrI',
                apiUrl: 'http://localhost:3000'
            }
        },
        components: {
            Navigation,
            Upload,
            Result
        },
        methods: {
            catchUrl(payload){
                this.isUpload = false
                this.imageUrl = payload
            }
        },
        created(){

        }
    }
</script>
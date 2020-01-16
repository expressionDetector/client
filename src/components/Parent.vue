<template>
    <div>
        <Navigation />
        <Upload />
    </div>
</template>
<script>
    import Navigation from "./general/Nav.vue";
    import Upload from "./upload/Upload";
    export default{
        data(){
            return {

            }
        },
        components: {
            Navigation,
            Upload
        },
        methods: {},
        created(){

        }
    }
</script>
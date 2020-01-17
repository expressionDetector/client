<template>
    <div>
        <div class="row">
            <div class="col-6">
                <img :src="imageUrl" alt="..." class="shadow-sm" height="500" style="height: 500px !important; width: 100%">
            </div>
            <div class="col-6 p-3 ">
                <h2>Your emotions</h2>
                <div v-if='!results.Joy'>
                    <div class="d-flex justify-content-center mb-3">
                        <b-spinner label="Loading..." variant="primary"></b-spinner>
                    </div>
                </div>
                <div class="mt-4"></div>
                <template v-for="(value, name) in results">
                    <div class="row">
                        <div class="col-sm-2">
                            <label>{{name}}:</label>
                        </div>
                        <div class="col-sm-10 ">
                            <b-progress :value="value" show-progress class="mb-3" style="height: 25px"></b-progress>
                        </div>
                    </div>
                </template>
                 <div class="mt-3">
                    <div v-if='status == "loading"' class="spinner-border mb-4" role="status"></div>
                    <span v-if='status == "success"' class="alert alert-primary mb-4">Share success</span>
                    <span v-if='status == "failed"' class="alert alert-danger mb-4">Share failed</span>
                    <div class="mt-3"></div>
                     <div class="btn-group" role="group" aria-label="Basic example">
                        <button type="button" class="btn btn-danger " @click="share">Pinterest</button>
                        <a :href="`https://twitter.com/intent/tweet?text=Try%20my%20new%20app%20Expression%20Detector. ${imageUrl}`" class="btn btn-primary" target="_blank" >Twiter</a>
                        <a :href="`https://www.facebook.com/sharer.php?u=${imageUrl}`" class="btn btn-primary" target="_blank">Facebook</a>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>

export default {
    data(){
        return {
        }
    },
    props: ['imageUrl', 'results', 'status', 'message'],
    methods: {
        share(){
            this.$emit('share')
        }
    }
}
</script>

<style scoped>
    .fade-enter-active, .fade-leave-active {
    transition: opacity .5s;
    }
    .fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
    opacity: 0;
    }
</style>
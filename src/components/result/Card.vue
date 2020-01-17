<template>
    <div>

        <div class="row">
            <div class="col-4">
                <img :src="imageUrl" alt="..." class="img-thumbnail" height="400" style="height: 300px !important; width: 100%">
            </div>
            <div class="col-8 p-3 ">
                <div v-if='!results.Joy'>
                    <div class="d-flex justify-content-center mb-3">
                        <b-spinner label="Loading..." variant="primary"></b-spinner>
                    </div>
                </div>
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
    props: ['imageUrl', 'results']
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
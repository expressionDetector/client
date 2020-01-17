<template>
    <div>

        <div class="row">
            <div class="col-6">
                <img :src="imageUrl" alt="..." class="shadow-sm" height="500" style="height: 500px !important; width: 100%">
            </div>
            <div class="col-6 p-3 ">
                <h2>Your emotionals</h2>
                <div v-if='!results.Joy'>
                    <div class="d-flex justify-content-center mb-3">
                        <b-spinner label="Loading..." variant="primary"></b-spinner>
                    </div>
                </div>
                <div class="mt-5"></div>
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
                    <b-button-group>
                    <b-button variant="danger">Pinterest</b-button>
                    <b-button variant="info">Twiter</b-button>
                    </b-button-group>
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
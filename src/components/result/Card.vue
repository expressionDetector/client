<template>
    <div class="row">
        <div class="col-4">
            <img :src="imageUrl" alt="..." class="img-thumbnail" height="400" style="height: 300px !important; width: 100%">
        </div>
        <div class="col-8 p-3 ">
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


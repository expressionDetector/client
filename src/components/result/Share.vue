<template>
    <div>
        <h4 class="m-3">Share to: </h4>
        <button @click='share' class="btn ml-4"><img src="//assets.pinterest.com/images/pidgets/pinit_fg_en_round_red_32.png" /></button>
        <div v-if='status == "loading"' class="spinner-border ml-3" role="status"></div>
        <span v-if='status == "success"' class="alert alert-primary ml-3">Share success</span>
        <span v-if='status == "failed"' class="alert alert-danger ml-3">Share failed</span>
        <a class="btn btn-primary d-block col-md-1 ml-3 mt-3"
            target="_blank" 
            :href='`https://twitter.com/intent/tweet?text=Try%20my%20new%20app%20Expression%20Detector. ${url}`'>
        Tweet</a>
    </div>
</template>

<script>
export default {
    data(){
        return {
        }
    },
    props: ['status', 'message', 'url'],
    methods: {
        share(){
            this.$emit('share')
        }
    }
}
</script>
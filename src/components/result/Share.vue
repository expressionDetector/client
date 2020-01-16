<template>
    <div>
        <button @click='share'>Share</button>
    </div>
</template>

<script>
export default {
    data(){
        return {

        }
    },
    methods: {
        share(){
            this.$emit('share')
        }
    }
}
</script>
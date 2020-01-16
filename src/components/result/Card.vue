<template>
    <div>
        <div class="container justify-content-center d-flex  mt-3">
            <b-card img-src="https://placekitten.com/300/300" img-alt="Card image" img-left class="mb-3" style="width: 80% !important">
                <b-card-text>
                    <b-badge variant="success">image detected</b-badge>
                    <hr>
                    <div class="row mb-1">
                        <div class="col-sm-2">
                            <label for="">Joy:</label>
                            <!-- <span>Joy</span> -->
                        </div>
                        <div class="col-sm-10 pt-1">
                            <b-progress :value="'15'" show-progress class="mb-3"></b-progress>
                        </div>
                    </div>
                </b-card-text>
            </b-card>
        </div>
    </div>
</template>

<script>

export default {
    data(){
        return {
            emotionals: {
                Joy: null,
                Sorrow: null,
                Anger: null,
                Surprise: null,
                Exporesed: null,
                Blurred: null,
                Headwear: null
            }
        }
    },
    props: []
}
</script>


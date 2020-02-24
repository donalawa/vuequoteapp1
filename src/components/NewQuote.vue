<template>
    <div class="row">
        <form>
            <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
                <h2>Enter New Quote</h2>
                <textarea class="form-control" rows="3" cols="100" v-model="quote"></textarea>
            </div>
            <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
               <button class="btn btn-primary" @click.prevent="createNew">Add Quote</button>
            </div>
        </form>
    </div>
</template>

<script>

export default {
    data(){
        return {
            quote: ''
        }
    },
    methods: {
        createNew(){
            this.$emit('newQuote', this.quote);
            this.quote = '';
        }
    }
}
</script>

<style scoped>
    h2 {
        box-sizing: border-box;
        font-size: 1.4rem;
        border: solid 10px transparent;
        border-image: linear-gradient(to top right, #009ffd, #2a2a72);
        border-image-slice: 1;
        background-color: #2a2a72;
        color: white;
        text-align: center;
    }
</style>
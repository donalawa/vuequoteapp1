<template>
   <div id="app" class="container">
      <app-header :quoteCount="quotes.length" :maxQuotes="maxQuotes"></app-header>
      <hr>
      <div class="alert alert-warning" v-if="showWarning">Please You have reach the max quote you need to delete some quotes before adding</div>
      <app-newquote @newQuote="createQuote"></app-newquote>
      <h2>My Life Quotes</h2>
      <app-quotegrid :quotes="quotes" @newDelete="deleteNow"></app-quotegrid>
   </div>
</template>

<script>
import QuoteGrid from './components/QuoteGrid.vue';
import NewQuote from './components/NewQuote.vue';
import Header from './components/Header.vue'
export default {
  data(){
    return {
      quotes: ['Just a Quote to see something','Some Second Quote Good'],
      maxQuotes: 8,
      showWarning: false,
    }
  },
  components: {
    'app-quotegrid': QuoteGrid,
    'app-newquote': NewQuote,
    'app-header': Header
  },
  methods: {
    createQuote(e){
      if(this.quotes.length < this.maxQuotes) {
        this.quotes.push(e)
      }
      
    },
    deleteNow(index){
      this.quotes.splice(index,1);
    }
  },
  watch: {
    quotes: function(value){
      if(value.length >= this.maxQuotes){
        this.showWarning = true;
      }

      if(value.length < this.maxQuotes){
        this.showWarning = false;
      }
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
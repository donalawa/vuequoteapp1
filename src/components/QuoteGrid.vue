<template>
    <div class="row">
        <app-quote v-for="(quote,index) in quotes" :key="index" @click.native="deleteQuote(index)">
            {{ quote }}
            </app-quote>
    </div>
</template>

<script>
import Quote from './Quote.vue'
export default {
  props: ['quotes'],
  components: {
      appQuote: Quote
  },
  methods: {
      deleteQuote(Qindex){
           this.$emit('newDelete', Qindex)

      }
  }
}
</script>

<style scoped>
    .row {
         background-color: #eceff1;
         padding: 20px;
    }
</style>
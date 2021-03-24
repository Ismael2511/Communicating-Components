<template>
    <div class="container">
      <Header :maxQuotes="maxQuotes" :quoteCount="quotes.length"/>
      <NewQuote @quoteAdd="newQuote"/>
      <QuoteGrid :quotes="quotes" @quoteDelete="deletedQuote"/>
      <div class="row">
        <div class="col-sn-12 text-center">
          <div class="alert alert-info">Info: Click on a Quote to delete it!</div>
        </div>
      </div>
    </div>
</template>

<script>
  import QuoteGrid from './components/QuoteGrid.vue'
  import Header from './components/Header.vue'
  import NewQuote from './components/NewQuote.vue'

    export default {
      components: {
        QuoteGrid,
        NewQuote,
        Header
      },
        data: () => {
          return{
            quotes: ['Just a quote to see something'],
            maxQuotes: 10
          }
        },
        methods: {
          newQuote(quote){ 
            if(this.quotes.length >= this.maxQuotes) return alert('Please delete some quotes first')

            this.quotes.push(quote) 
          },
          deletedQuote(index){
            this.quotes.splice(index,1);
          }
        }
    }
</script>

<style>
</style>

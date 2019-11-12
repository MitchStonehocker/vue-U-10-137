<template>
  <div class="container">
    <app-header :quoteCount="quotes.length" :maxQuotes="maxQuotes"></app-header>
    <app-new-quote @quoteAdded="newQuote"></app-new-quote>
    <app-quote-grid :quotes="quotes" @quoteDeleted="quoteDeleted"></app-quote-grid>
    <div class="row">
      <div class="col-sm-12 text-center">
        <div class="alert alter-info">
          Info: Click on a quote to delete it.
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import QuoteGrid from './components/QuotesGrid.vue'
import NewQuote from './components/NewQuote'
import Header from './components/Header'

export default {
  data: function () {
    return {
      quotes: [
        'just a quote...'
      ],
      maxQuotes: 10
    }
  },
  methods: {
    newQuote (quote) {
      if (this.quotes.length >= this.maxQuotes) {
        return alert(`You have reach your maximum of ${this.maxQuotes} quotes. Please delete a quote to add a new quote.`)
      } else {
        this.quotes.push(quote)
      }
    },
    quoteDeleted (index) {
      this.quotes.splice(index, 1)
    }
  },
  components: {
    appQuoteGrid: QuoteGrid,
    appNewQuote: NewQuote,
    appHeader: Header
  }
}
</script>

<style scoped>

</style>

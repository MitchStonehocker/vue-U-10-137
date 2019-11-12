<template>
  <div class="row">
    <div class="col-sm-8-sm-offset-2.col-xs-12.col-md-6.col-md-offset-3">
      <label for="">Quote</label>
        <textarea class="form-control" name="" id="" cols="30" rows="3" v-model="quote"></textarea>
      </div>
      <div class="col-sm-8-sm-offset-2.col-xs-12.col-md-6.col-md-offset-3">
      <button class="btn btn-primary" @click.prevent="createNewQuote">Add Quote</button>
    </div>
  </div>
</template>

<script>
export default {
  data: function () {
    return {
      quote: ''
    }
  },
  methods: {
    createNewQuote () {
      this.$emit('quoteAdded', this.quote)
      this.quote = ''
    }
  }
}
</script>

<style scoped>

</style>

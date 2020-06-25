<template>
  <div class="row">
    <form>
      <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3">
        <label>Quote</label>
        <textarea rows="3" class="form-control" v-model="quote"></textarea>
      </div>
      <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3">
        <button class="btn btn-primary" @click.prevent="createNew">Add Quote</button>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  props: ["quotes"],
  data: function() {
    return {
      quote: ""
    };
  },
  methods: {
    createNew() {
      if (this.quotes.length >= 10) {
        return alert("Please delete Quotes first");
      }
      this.$emit("quoteAdded", this.quote);
      this.quote = "";
    }
  }
};
</script>

<style scoped>
</style>
<template>
    <form action="">
        <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
            <label for="">quote</label>
            <textarea name="" rows="3" class="form-control" placeholder="Add new Quote..." v-model="quote"></textarea>
        </div>
        <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
            <button class="btn btn-primary" @click.prevent= "createNew">Add Quote</button>
        </div>
    </form>
</template>

<script>
export default {
    data: function () {
        return {
            quote: ''
        }
    },
    methods: {
        createNew () {
            this.$emit('quoteAdded', this.quote);
            this.quote = ''
        }
    }

}
</script>

<style scoped>

</style>
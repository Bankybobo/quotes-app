<template>
    <section class="row">
        <app-quote v-for="(quote, index) in quotes" > 
            <div class="col-md-12">
                {{ quote }}
            </div>
            <div class="col-md-12 mt-5">
                <button @click.prevent= "deleteQuote(index)" class="btn btn-block">Delete Quote</button>
            </div>
            
            
        </app-quote>
    </section>
    
</template>

<script>
import  Quote  from "./Quote.vue";
export default {
    props: ['quotes'],
    components: {
        appQuote: Quote
    },
    methods: {
        deleteQuote(index) {
            this.$emit("quoteDelete", index)
        }
    }    
}
</script>

<style scoped>
.btn {
    
    font-size: 15px;
    color: white;
    background: rgb(97, 83, 3);
}
</style>
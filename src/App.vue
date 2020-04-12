<template>
    <section class="container text-center">
            <!-- <div class="row text-center">
                <div class="progress " :style="{width: progressLength()}">{{quotesArray.length}} / 10</div>
            </div> -->
            <app-header :quoteCount="quotesArray.length" :maxQuotes="maxQuotes"></app-header>
             <app-new-quote @quoteAdded="newQuote"></app-new-quote>
             <app-quote-grid :quotes="quotesArray" @quoteDelete="deleteQuote"></app-quote-grid>
             <div class="row">
                 <div class="col-md-12 mt-5 text-center">
                     <div class="alert alert-info">Info: Click on a quote to delete it</div>
                 </div>
             </div>
    </section>
</template>

<script>
import QuoteGrid from './components/QuoteGrid.vue';
import NewQuote from './components/NewQuote.vue';
import Header from './components/Header.vue';
 
    export default {
        data: function () {
            return {
                quotesArray: ["I am Adedara Bankole and this is a random quote", "Hello, I am a Vue Developer"],
                maxQuotes: 10
            }
        },
        methods: {
            newQuote (quote) {
                if(this.quotesArray.length >= 10 || quote.trim() === '')
                return;
                this.quotesArray.push(quote)
                console.log()
            },
            deleteQuote (x) {
                this.quotesArray.splice(x, 1)
            },
            progressLength () {
                return this.quotesArray.length * 100 + "px"
            }
        },
        components: {
            appQuoteGrid: QuoteGrid,
            appNewQuote: NewQuote,
            appHeader: Header
        }
    }
</script>

<style>
/* .progress {
    height: 20px;
    background-color: rgb(8, 8, 70);
    margin-top: 30px;
    color: white;
    text-align: center;
    transition: width 1.2s;
} */
</style>

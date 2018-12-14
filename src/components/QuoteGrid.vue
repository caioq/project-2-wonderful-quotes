<template>
    <div class="row">
        <app-quote 
            v-for="(quote, index) in quotes" 
            :key="index"
            @click.native="deleteQuote(index)">
            {{ quote }}
        </app-quote>
    </div>
</template>

<script>
    import Quote from './Quote.vue';
    import { eventBus } from '../main';

    export default {
        data: function () {
            return {
                quotes: [],
                maxQuotes: 10
            }
        },
        components: {
            appQuote: Quote
        },
        methods: {
            deleteQuote(index) {
                this.quotes.splice(index, 1);            
            }
        },
        created() {
            console.log('created');
            eventBus.$on('quoteAdded', (quote) => {
                if (this.quotes.length < this.maxQuotes) {
                    this.quotes.push(quote);
                }
            });
        }
    }
</script>

<style>

</style>

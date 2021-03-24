<template>
    <div class="row">
        <Quotes v-for="(el,index) in quotes" :key="index" @click.native="deleteQuote(index)"><h1 slot="quote">{{el}}</h1></Quotes>
    </div>
</template>

<script>
import Quotes from './Quote.vue'
export default {
    props:['quotes'],
    components: {
        Quotes
    },
    methods: {
        deleteQuote(index){
            this.$emit('quoteDelete', index)
        }
    }
}
</script>

<style scoped>

</style>
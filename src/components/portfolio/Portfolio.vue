<template>
  <div>
    <p v-if="stocks == 0" class="red--text display-1">Você não tem nenhuma ação em seu portfolio!</p>
    <v-layout row wrap v-else>
        <Stock v-for="stock in stocks" :key="stock.id" :stock="stock" />
    </v-layout>
    </div>
</template>

<script>
import Stock from './Stock'
// import { mapGetters} from 'vuex'
export default {
    components: { Stock },
    computed: {
        // // ...mapGetters({
        // //   stocks: 'stockPortfolio'
        // }),
        stocks() {
            return this.$store.getters.stockPortfolio
        }
    }
}
</script>

<style>

</style>
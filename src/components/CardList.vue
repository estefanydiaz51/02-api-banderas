<template>
    <div class="row">
        <div 
            class="col-12"
            v-for="(pais, index) in paises" :key="index"
        >
            <Card :pais="pais"></Card>
        </div>
    </div>
</template>

<script>
import Card from './Card'
import { computed, onMounted } from '@vue/runtime-core'
import { useStore} from 'vuex'
export default {
  components: { Card },
    setup() {
        const store = useStore();

        // para state con computed
        // const paises = computed( () => {
        //     return store.state.paises;
        // })

         const paises = computed( () => {
            return store.getters.topPaisesPoblacion;
        })


        onMounted( async() => {
            // dispatch es para action
            await store.dispatch( 'getPaises' );
            await store.dispatch('filtrarRegion', 'Americas');
        })

        return { paises }
    }

}
</script>

<style>

</style>
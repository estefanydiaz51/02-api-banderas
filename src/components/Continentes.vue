<template>
    <div class="text-center mb-3">
        <h3> Filtrar por Continente</h3>
        <div class="btn-group">
            <div class="btn btn-dark" @click="filtro('Americas')">AM</div>
            <div class="btn btn-dark" @click="filtro('Europe')">EU</div>
            <div class="btn btn-dark" @click="filtro('Asia')">AS</div>
            <div class="btn btn-dark" @click="filtro('Oceania')">OC</div>
            <div class="btn btn-dark" @click="filtro('Africa')">AF</div>
            <div class="btn btn-dark" @click="filtro('')">ALL</div>
        </div>
    </div>
</template>

<script>
import { useStore } from 'vuex'
export default {

    setup(){
        const store = useStore();

        const filtro = ( region ) => {
            store.dispatch('filtrarRegion', region);
        }
        return { filtro }
    }

}
</script>

<style>

</style>
<template>
    <div class="container">
        <h1>Paises API</h1>
        <Continentes></Continentes>
        <Buscador></Buscador>
        <CardList></CardList>
    </div>  
</template>

<script>

import Buscador from './components/Buscador'
import Continentes from './components/Continentes'
import CardList from './components/CardList'
export default {
    name: 'App',
    components: {
    Buscador,
    Continentes,
    CardList,
    }
}
</script>

<style>

</style>

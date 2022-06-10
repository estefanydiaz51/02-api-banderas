<template>
    <div class="card mb-3">
        <div class="card-body">
            <h5>{{ pais.name.common }}</h5>
            <p class="text-center">
                <img :src="pais.flags[1]" :alt="`bandera-${pais.name.common}`" class="img-fluid w-50">
            </p>
            <p class="card-text">
                <span class="badge badge-dark d-block mb-1">
                    Nativename: {{ pais.name.nativeName }}
                </span>
                <span class="badge badge-info p-3 d-block mb-1">
                    Population: {{ numeroFormato( pais.population ) }}
                </span>
                <span class="badge badge-dark d-block mb-1">
                    Capital: {{ pais.capital ? pais.capital[0] : '' }}
                </span>
                 <span class="badge badge-dark d-block mb-1">
                    Region: {{ pais.region }}
                </span>
            </p>
        </div>
    </div>
</template>

<script>
export default {
    props: ['pais'],
    setup(){
        const numeroFormato = ( number ) => {
            return new Intl.NumberFormat("de-DE").format( number );
        } 

        return { numeroFormato }
    }
}
</script>

<style>

</style>
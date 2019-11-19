<template>
    <div>
        <h1>Galeria : </h1>
        <router-link :to="{name: 'fotos', params: {id : item}}" 
            v-for="(item, index) of fotosArreglo" :key="index">
            <button> {{ item }} </button>
        </router-link>
        <foto></foto>

        <button class="btn btn-secondary" @click="anterior">anterior</button>
        <button class="btn btn-success" @click="home">Volver al home</button>
        <button class="btn btn-secondary" @click="siguiente">siguiente</button>

    </div>

</template>

<script>
import Foto from "@/components/Fotografia.vue";

export default {
    name: 'Fotos',
    components:{
        Foto
    },
    data(){
        return {
         fotosArreglo: [1,2,3]
        }
    },
    methods:{
        home(){
            this.$router.push('/')
        },
        anterior(){
            this.$router.go(-1)
        },
        siguiente(){
            this.$router.go(1)
        }
    }
}
</script>
<template>
    <div class="row row-cols-5 mygap">
        <AlbumCard v-for="disco in listaDischi" :key="disco.poster" :axiosObject="disco"></AlbumCard>
    </div>
</template>

<script>
import AlbumCard from './AlbumCard.vue'
import axios from "axios"
export default {
    components:{
        AlbumCard
    },
    data() {
        return {
            listaDischi:[],
        }
    },
    mounted() {
        axios.get("https://flynn.boolean.careers/exercises/api/array/music")
        .then((AxiosResponse)=>{
            this.listaDischi=AxiosResponse.data.response
            console.log(this.listaDischi);
        })
    },
}
</script>

<style lang="scss">
    .mygap{
        row-gap: 2rem;
    }
</style>
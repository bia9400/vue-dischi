<template>
    <div>
        <AlbumCard></AlbumCard>
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
    
</style>
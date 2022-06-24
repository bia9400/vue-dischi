<template>
<div class=" ">
    <h2 class="text-white">Choose Genre</h2>
        <div class="selectyyy py-4">
            <select class="form-select " v-model="choosenGenre" @change="filterArray(choosenGenre)" aria-label="Default select example">
          <option selected ></option>
          <option v-for="genre in selectValues" :key="genre"  >{{genre}}</option>
          
        </select>
        </div>
      
    
    <div class="row row-cols-5 mygap">
        <AlbumCard v-for="disco in listaDischi" :key="disco.poster" :axiosObject="disco" ></AlbumCard>
    </div>
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
            selectValues:["Rock","Pop","Jazz","Metal"],
            choosenGenre:"",
            pritedArray:[]
        }
    },
    mounted() {
        axios.get("https://flynn.boolean.careers/exercises/api/array/music")
        .then((AxiosResponse)=>{
            this.listaDischi=AxiosResponse.data.response
            console.log(this.listaDischi);
        })
        
    },
    methods: {
        filterArray(choosenGenre){
           for(let i=0;i<this.listaDischi.length;i++){
            if(this.listaDischi[i].genre!=choosenGenre){
                this.listaDischi.splice(i,1)
            }
           }
            console.log(choosenGenre);
            console.log(this.listaDischi);
        }
    },
}
</script>

<style lang="scss">
    .mygap{
        row-gap: 2rem;
    }
    .selectyyy{
        width: 30%;
    }
</style>
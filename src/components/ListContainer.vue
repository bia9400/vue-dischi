<template>
<div class=" ">
    <h2 class="text-white">Choose Genre</h2>
        <div class="selectyyy py-4">
            <select class="form-select " v-model="choosenGenre" @change="filterArray(choosenGenre)" aria-label="Default select example">
          <option selected ></option>
          <option v-for="genre in selectValues" :key="genre"  >{{genre}}</option>
          
        </select>
        </div>
      
    
    <div v-if="printedArray.length<=0" class="row row-cols-5 mygap">
        <AlbumCard  v-for="disco in listaDischi" :key="disco.poster" :axiosObject="disco" ></AlbumCard>
    </div>
    <div v-else class="row row-cols-5 mygap">
        <AlbumCard  v-for="disco in printedArray" :key="disco.poster" :axiosObject="disco" ></AlbumCard>
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
            printedArray:[]
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
            this.printedArray=[]
            console.log(choosenGenre);
           this.listaDischi.forEach((value)=>{
            if(choosenGenre==value.genre){
                this.printedArray.push(value)
            }
           })
           console.log(this.printedArray);
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
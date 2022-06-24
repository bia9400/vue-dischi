<template>
    <div>
        <select class="form-select" v-model="choosenGenre" aria-label="Default select example">
          <option selected>Choose your Genre</option>
          <option v-for="genre in selectValues" :key="genre"  onchange="$emit(`search`)">{{genre}}</option>
          
        </select>
      
    </div>
</template>
<script>

export default {
    data() {
        return {
            selectValues:["Rock","Pop","Jazz","Metal"],
            choosenGenre:"",
        }
    },
    
}
</script>

<style lang="scss">
    
</style>
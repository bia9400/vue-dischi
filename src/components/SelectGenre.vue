<template>
    <div>
        <select class="form-select" v-model="choosenGenre" aria-label="Default select example">
          <option selected></option>
          <option v-for="genre in selectValues" :key="genre"  @mouseenter="$emit(`search`,choosenGenre)">{{genre}}</option>
          
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
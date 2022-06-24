<template>
  <div id="app">
    <header class="d-flex justify-content-between">
      <div class="logo-container ">
        <img src="../public/logo-small.svg" alt="" />
      </div>
      
     <SelectGenre @search="filterAlbum"></SelectGenre>
    </header>
    <main>
      <div class="container py-4">
        <ListContainer></ListContainer>
      </div>
    </main>
  </div>
</template>

<script>
import ListContainer from "./components/ListContainer.vue";
import SelectGenre from './components/SelectGenre.vue'
export default {
  name: "App",
  components: { ListContainer,
  SelectGenre },
  
    methods: {
        filterAlbum(ddd){
            console.log(ddd);
        }
    }
};
</script>

<style lang="scss">
@import url(../node_modules/bootstrap);
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
body {
  height: 100vh;
  background-color: #1e2d3b;
}
.logo-container {
  height: 50px;
  aspect-ratio: 1;
}
header {
  padding: 1rem 0.5rem;
  background-color: #2e3a46;
}
</style>

<template>
  <div class="col ">
    <div class="card text-center" style="width: 18rem">
      <img :src="axiosObject.poster" class="card-img-top m-auto" alt="..." />
      <div class="card-body">
        <h5 class="card-title text-white text-uppercase">{{ axiosObject.title }}</h5>
        <p class="card-text">
          {{ axiosObject.genre }}
        </p>
        <p class="card-text">
          {{ axiosObject.year }}
        </p>
      </div>
    </div>
  </div>
</template>


<script>
export default {
  props: {
    axiosObject: Object,
  },
};
</script>

<style lang="scss">
.card {
  background-color: #2e3a46 !important;
  min-height: 400px;

  img {
    width: 200px;
    aspect-ratio: 1;
  }
  p {
    color: #7e776f;
  }
}
</style>
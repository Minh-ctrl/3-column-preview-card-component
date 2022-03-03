<script>
import CarCard from "./components/CarCard.vue";

export default {
  components:{
    CarCard
  }
}
</script>

<template>
  <main>
    <div class="container">
      <CarCard title="SEDANS" sedans class="orange" />
      <CarCard title="LUXURY" luxury class="cyan" />
      <CarCard title="SUVS" suv class="dark-cyan" />
    </div>
  </main>
</template>

<style>
@import "./assets/base.css";
.container {
  display: flex;
  flex-flow: row wrap;
  justify-content: space-around;
  height: 20rem;
}
.orange {
  background-color: hsl(31, 77%, 52%);
}
.cyan {
  background-color: hsl(184, 100%, 22%);
}
.dark-cyan {
  background-color: hsl(179, 100%, 13%);
}
</style>

<script setup>
import IconLuxury from "./iconss/IconLuxury.vue";
import IconSUVs from "./iconss/IconSUVs.vue";
import IconSedans from "./iconss/IconSedans.vue";
defineProps({
  title: {
    type: String,
    required: true,
  },
  luxury: {
    type: Boolean,
  },
  suv: {
    type: Boolean,
  },
  sedans: {
    type: Boolean,
  },
});
</script>
<script>
export default {
  data() {
    return {
      sedans:
        "Choose a sedan for its affordability and excellent fuel economy. Ideal for cruising in the city or on your next road trip",
      luxury:
        "Take an SUV for its spacious interior, power and versatility. Perfect for your next family vacation and off-road adventures",
      suvs: "Cruise in the best car brands without the bloated prices. Enjoy the enhanced comfort of a luxury rental and arrive in style",
      color: "hsl(31, 77%, 52%);",
    };
  },
};
</script>
<template>
  <div class="wrapper">
    <IconLuxury class="svg" v-if="luxury" />
    <IconSUVs class="svg" v-if="suv" />
    <IconSedans class="svg" v-if="sedans" />
    <h1 class="title">{{ title }}</h1>

    <p class="description" v-if="sedans">
      {{ this.sedans }}
    </p>
    <p class="description" v-if="luxury">
      {{ this.luxury }}
    </p>
    <p class="description" v-if="suv">{{ this.suvs }}</p>
    <button class="btn-orange" v-if="sedans">Learn More</button>
    <button class="btn-cyan" v-if="luxury">Learn More</button>
    <button class="btn-dark-cyan" v-if="suv">Learn More</button>
  </div>
</template>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Big+Shoulders+Display:wght@700&family=Lexend+Deca&display=swap");
.wrapper {
  display: flex;
  flex-flow: column nowrap;
  height: fit-content;
  width: fit-content;
  max-height: 1000px;
  max-width: 250px;
  border-radius: 5%;
  justify-content: center;
  align-items: center;
}
.svg {
  margin: 2rem 1.5rem 1.5rem 1.5rem;
  align-self: flex-start;
}
.title {
  margin: 0rem 1.5rem 1.5rem 1.5rem;
  align-self: flex-start;
  color: hsla(0, 0%, 100%, 0.89);
  font-family: "Big Shoulders Display", cursive;
  font-weight: 400;
  letter-spacing: -0.1rem;
}
.description {
  /* padding: 1rem; */
  margin: 1rem;
  color: var(--text-color);
  font-family: "Lexend Deca", sans-serif;
}
button {
  margin: 3rem 1rem 1rem 1rem;
  border-radius: 500px;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  min-width: 20ch;
  min-height: 50px;
  text-decoration: none;
  font-family: "Big Shoulders Display", cursive;
  border: none;
  align-self: flex-start;
}
.btn-orange {
  color: hsl(31, 77%, 52%);
}
.btn-cyan {
  color: hsl(184, 100%, 22%);
}
.btn-dark-cyan {
  color: hsl(179, 100%, 13%);
}
</style>
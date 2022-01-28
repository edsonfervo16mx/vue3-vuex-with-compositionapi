<template>
  <div class="card mb-2">
    <h5 class="text-center">{{ pais.name }}</h5>
    <p class="text-center">
      <img :src="pais.flag" :alt="pais.name" class="img-fluid w-50" />
    </p>
    <p class="card-text">
      <span class="badge bg-dark d-block mb-1">{{ pais.nativeName }}</span>
      <span class="badge bg-info p-3 d-block mb-1">{{ pais.capital }}</span>
      <span class="badge bg-dark d-block mb-1">{{
        numeroFormato(pais.population)
      }}</span>
      <span class="badge bg-dark d-block mb-1">{{ pais.region }}</span>
    </p>
  </div>
</template>

<script>
export default {
  props: ["pais"],
  setup() {
    const numeroFormato = (num) => {
      return new Intl.NumberFormat("en-DE").format(num);
    };

    return {
      numeroFormato,
    };
  },
};
</script>

<style></style>

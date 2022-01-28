<template>
  <input
    type="text"
    placeholder="Ingrese pais"
    class="form-control my-3"
    v-model="texto"
    @keyup="procesarInput"
  />
</template>

<script>
import { useStore } from "vuex";
import { ref } from "vue";
export default {
  setup() {
    const texto = ref("");
    const store = useStore();

    const procesarInput = () => {
      console.log(texto.value);
      store.dispatch("filtroNombre", texto.value);
    };

    return {
      texto,
      procesarInput,
    };
  },
};
</script>

<style></style>

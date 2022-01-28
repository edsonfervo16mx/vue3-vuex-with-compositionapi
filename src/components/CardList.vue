<template>
  <div class="row">
    <div class="col-lg-12" v-for="pais in paises" :key="pais.name">
      <Card :pais="pais" />
    </div>
  </div>
</template>

<script>
import Card from "@/components/Card";
import { computed, onMounted } from "vue";
import { useStore } from "vuex";
export default {
  components: { Card },
  setup() {
    const store = useStore();

    onMounted(async () => {
      await store.dispatch("getPaises");
      await store.dispatch("filtrarRegion", "Americas");
    });

    const paises = computed(() => {
      //return store.state.paises;
      return store.getters.topPaisesPoblacion;
    });

    return {
      paises,
    };
  },
};
</script>

<style></style>

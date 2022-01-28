<template>
  <div class="text-center">
    <h4>Filtrar por continente</h4>
    <div class="btn-group mb-2">
      <button class="btn btn-primary" @click="getPaisesList('Americas')">
        AM
      </button>
      <button class="btn btn-primary" @click="getPaisesList('Europe')">
        EU
      </button>
      <button class="btn btn-primary" @click="getPaisesList('Asia')">AS</button>
      <button class="btn btn-primary" @click="getPaisesList('Oceania')">
        OC
      </button>
      <button class="btn btn-primary" @click="getPaisesList('Africa')">
        AF
      </button>
      <button class="btn btn-primary" @click="getPaisesList('')">ALL</button>
    </div>
  </div>
</template>

<script>
import { useStore } from "vuex";
export default {
  setup() {
    const store = useStore();

    const getPaisesList = async (region) => {
      await store.dispatch("filtrarRegion", region);
    };

    return {
      getPaisesList,
    };
  },
};
</script>

<style></style>

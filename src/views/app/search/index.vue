<template>
  <div>
    <h2>Search</h2>

    <b-row>
      <b-col lg="8" md="8" sm="12"> </b-col>
      <b-col lg="4" md="4" sm="12">
        <privatemode class="mb-3" />
        <types class="mb-3" />
      </b-col>
    </b-row>
  </div>
</template>

<script>
import privatemode from "../../../components/Qavah/privatemode.vue";
import types from "../../../components/Qavah/search/types.vue";
export default {
  name: "search",
  components: {
    types,
    privatemode,
  },
};
</script>

<style>
</style>
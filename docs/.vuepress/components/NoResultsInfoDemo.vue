<template>
  <div>
    <div class="pl-1 pb-2 pt-3">Selected Country: {{ query }}</div>

    <h2>Using the <code>noResultsInfo</code> slot</h2>
    <vue-bootstrap-autocomplete
      class="mb-4"
      :data="[
        'Canada',
        'United Kingdom',
        'United States',
        'Mexico',
        'Netherlands',
      ]"
      v-model="query"
      showOnFocus
      placeholder="Choose a country"
    >
      <template slot="noResultsInfo">
        <span>{{ noResultsInfo }} <b>{{ query }}</b></span>
      </template>
    </vue-bootstrap-autocomplete>

    <h2>Using the <code>noResultsInfo</code> prop</h2>
    <vue-bootstrap-autocomplete
      class="mb-4"
      :data="[
        'Canada',
        'United Kingdom',
        'United States',
        'Mexico',
        'Netherlands',
      ]"
      v-model="query"
      showOnFocus
      placeholder="Choose a country"
      no-results-info="No results found (using prop)"
    />
  </div>
</template>

<script>
import "bootstrap-vue/dist/bootstrap-vue.css";
import VueBootstrapAutocomplete from "../../../src/components/VueBootstrapAutocomplete";

export default {
  name: "NoResultsInfoDemo",
  components: { VueBootstrapAutocomplete },
  data() {
    return {
      query: "",
    };
  },
  computed: {
    noResultsInfo() {
      return `No results found for`;
    },
  },
};
</script>

<style lang="scss">
@import "bootstrap/scss/bootstrap.scss";
</style>

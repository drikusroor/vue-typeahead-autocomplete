<template>
  <div>
    <div class="my-2">
      <input type="checkbox" v-model="state" class="mb-2" /> Set valid state to {{!state}}
    </div>
    <div class="pl-1 pb-2 pt-3">Selected Country: {{query}}</div>
    <vue-bootstrap-autocomplete
      :state="state"
      class="mb-4"
      :data="['Canada', 'United Kingdom', 'United States', 'Mexico', 'Netherlands']"
      v-model="query"
      showOnFocus
      placeholder="Choose a country"
    />
  </div>
</template>

<script>
  import 'bootstrap-vue/dist/bootstrap-vue.css'
  import VueBootstrapAutocomplete from "../../../src/components/VueBootstrapAutocomplete";

  export default {
    name: "Invalid",
    components: {VueBootstrapAutocomplete},
    data() {
      return {
        query: '',
        state: null
      }
    }
  }
</script>

<style lang="scss">
  @import 'bootstrap/scss/bootstrap.scss';
</style>

<template>
  <div>
    <p v-if="loading">
      {{ loadingLocale }}
    </p>
    <div v-else class="mb-5 text-center">
      <input
        type="text"
        v-model="search"
        placeholder="enter something"
        class="p-2 text-black w-full"
      />
    </div>
    <ul v-if="countries" class="h-40 overflow-y-auto">
        <li v-for="country in countries" :key="country.name">
            {{ country.emoji }} {{ country.name }} Region: {{ country.region }}
        </li>
    </ul>
  </div>
</template>

<script>
import { ref } from "vue";
import searchCountries from "../composables/searchCountries";
import filterCountries from "../composables/filterCountries";

export default {
  name: "SolviaSearchCountries",
  props: {
    placeholderLocale: {
      type: String,
      required: true,
    },
    loadingLocale: {
      type: String,
      required: true,
    },
  },
  setup() {
    const search = ref("");

    const { countriesData, loading } = searchCountries();

    const { countries } = filterCountries(countriesData, search);

    return {
      search,
      countries,
      loading,
    };
  },
};
</script>
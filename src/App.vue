<template>
  <div class="flex items-center content-center justify-center h-screen">
    <div class="bg-blue-800 text-white rounded-lg border shadow-lg p-10 w-5/12">
      <div>
        <div class="m-auto">
          <Solvia msg="Solvia - Autocomplete search for country sample" />
        </div>
        <div class="mt-8 m-auto">
          <SolviaSearchCountries
            placeholderLocale="Filtering..."
            loadingLocale="loading..."
          />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Solvia from './components/Solvia.vue'
import SolviaSearchCountries from './components/SolviaSearchCountries.vue'

export default {
  name: 'App',
  components: {
    Solvia,
    SolviaSearchCountries
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

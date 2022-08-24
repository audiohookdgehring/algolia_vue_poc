<template>
  <ais-instant-search :search-client="searchClient" index-name="podcasts">
    <ais-search-box />
    <ais-hits>
      <template v-slot:item="{ item }">
        <h2>{{ item.title }} published by {{ item.publisher }}</h2>
      </template>
    </ais-hits>
    <ais-pagination />
  </ais-instant-search>
</template>

<script>
import algoliasearch from 'algoliasearch/lite';
import 'instantsearch.css/themes/satellite-min.css';

export default {
    name: 'AlgoliaSearch',
    data() {
        return {
            searchClient: algoliasearch(
                '032WC3B6ZG',
                '92af7d487c37a7a95bff764c5f8a5b16'
            ),
        };
    },
};
</script>

<style>
body {
  font-family: sans-serif;
  padding: 1em;
}
</style>
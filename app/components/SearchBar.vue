<template>
  <StackLayout>
    <SearchBar
      @submit="onSubmit($event)"
      @clear="onClear($event)"
      :text="mySearchText"
    ></SearchBar>
  </StackLayout>
</template>

<script lang="ts">
import { EventData } from 'tns-core-modules/data/observable/observable'
import { SearchBar } from 'tns-core-modules/ui/search-bar'
import { StackLayout } from 'tns-core-modules/ui/layouts/stack-layout'

export default {
  data() {
    return {
      mySearchText: 'Canada'
    }
  },
  methods: {
    onSubmit(args: EventData) {
      const searchBar = <SearchBar>args.object

      console.log('Submitted text: ' + searchBar.text)
    },
    onClear(args: EventData) {
      const searchBar = <SearchBar>args.object

      console.log('Search bar clear')
    }
  }
}
</script>

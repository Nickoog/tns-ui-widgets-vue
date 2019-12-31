<template>
  <StackLayout>
    <ListView for="item in myItems" @itemTap="onItemTap($event)">
      <v-template>
        <StackLayout orientation="horizontal">
          <Label :text="'id: ' + item.id" />
          <Label :text="item.name" />
        </StackLayout>
      </v-template>
    </ListView>
  </StackLayout>
</template>

<script lang="ts">
import { EventData } from 'tns-core-modules/data/observable/observable'
import { ListView, ItemEventData } from 'tns-core-modules/ui/list-view'
import { StackLayout } from 'tns-core-modules/ui/layouts/stack-layout'

interface DataItem {
  id: Number
  name: string
  isHeader: boolean
}

export default {
  data() {
    return {
      myItems: [] as DataItem[]
    }
  },
  methods: {
    getItems() {
      for (var i = 0; i < 50; i++) {
        this.myItems.push({ id: i, name: 'data name ' + i })
      }
    },
    onItemTap(args) {
      const item = this.myItems[args.index]
      alert('item tapped as ' + item.name)
    }
  },
  created() {
    this.getItems()
  }
}
</script>

<style scoped>
.my-progress {
  color: green;
}
</style>

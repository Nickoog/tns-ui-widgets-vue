<template>
  <StackLayout>
    <SegmentedBar
      :items="myItems"
      @selectedIndexChange="onSelectedIndexChange($event)"
      :selectedIndex="selectedIndex"
    >
    </SegmentedBar>
  </StackLayout>
</template>

<script lang="ts">
import { EventData } from 'tns-core-modules/data/observable/observable'
import {
  SegmentedBar,
  SegmentedBarItem
} from 'tns-core-modules/ui/segmented-bar'
import { StackLayout } from 'tns-core-modules/ui/layouts/stack-layout'

export default {
  data() {
    return {
      selectedIndex: 1,
      myItems: [] as SegmentedBarItem[]
    }
  },
  methods: {
    onSelectedIndexChange(args: EventData) {
      const segBar = <SegmentedBar>args.object

      alert('Item selected: ' + segBar.items[segBar.selectedIndex].title)
    },
    getItems() {
      for (let i = 1; i < 5; i++) {
        const item = new SegmentedBarItem()

        item.title = 'Tab ' + i
        this.myItems.push(item)
      }
    }
  },
  created() {
    this.getItems()
  }
}
</script>

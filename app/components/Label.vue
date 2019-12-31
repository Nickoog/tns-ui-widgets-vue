<template>
  <GridLayout @loaded="onGridLoaded($event)" rows="50, 50, 50, 50, 50">
    <Label class="h1 text-right" :text="labelText" row="1"></Label>
    <Label class="h2 text-center font-weight-bold" :text="labelText" row="2"></Label>
    <Label class="h3" :text="labelText1" row="3"></Label>
    <Label class="h4" :text="labelText2" textWrap="true" row="4"></Label>
  </GridLayout>
</template>

<script lang="ts">
import { EventData } from 'tns-core-modules/data/observable/observable'
import { Label } from 'tns-core-modules/ui/label'
import { GridLayout } from 'tns-core-modules/ui/layouts/grid-layout'

export default {
  data() {
    return {
      labelText: 'Data BOUND',
      labelText1: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco',
      labelText2: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco',
    }
  },
  methods: {
    onGridLoaded(args: EventData) {
      const gridLayout = <GridLayout>args.object
      const label = new Label()

      label.text = 'Tap New label'
      label.on('tap', () => {
        console.log('new label tapped')
      })

      gridLayout.addChild(label)
    }
  }
}
</script>

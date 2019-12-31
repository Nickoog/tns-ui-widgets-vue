<template>
  <!-- <StackLayout>
    <Button
      :text="buttonText"
      class="-primary"
      @tap="onTapped($event)"
    ></Button>
  </StackLayout> -->
  <GridLayout @loaded="onGridLoaded($event)" />
</template>

<script lang="ts">
import { EventData } from 'tns-core-modules/data/observable/observable'
import { Button } from 'tns-core-modules/ui/button'
import { GridLayout } from 'tns-core-modules/ui/layouts/grid-layout'

export default {
  data() {
    return {
      buttonText: 'Data BOUND'
    }
  },
  methods: {
    // onTapped(args: EventData) {
    //   const button = <Button>args.object
    //   //button.text = 'Button TAPPED'
    //   this.buttonText = 'Button TAPPED'
    //   console.log('Button tapped: ' + args.eventName)
    // },
    onGridLoaded(args: EventData) {
      const gridLayout = <GridLayout>args.object
      const btn = new Button()

      btn.text = 'Tap New Button'
      btn.on('tap', () => {
        console.log('new button tapped')
      })

      gridLayout.addChild(btn)
    }
  }
}
</script>

<template>
  <StackLayout>
    <Slider v-model="value" :minValue="myMinVal" :maxValue="myMaxVal" @valueChange="onValueChange($event)"></Slider>
    <Button text="tap" @tap="onBtnTap($event)"></Button>
  </StackLayout>
</template>

<script lang="ts">
import { EventData } from 'tns-core-modules/data/observable/observable'
import { Slider } from 'tns-core-modules/ui/slider'
import { StackLayout } from 'tns-core-modules/ui/layouts/stack-layout'

export default {
  data() {
    return {
      myMinVal: -100,
      myMaxVal: 200,
      value: -50
    }
  },
  methods: {
    onValueChange(args: EventData) {
      const myControl = <Slider>args.object
      console.log('new value: ', myControl.value)
    },
    onBtnTap(args: EventData) {
      console.log(this.value)
      this.value = 200
    }
  }
}
</script>

<style scoped>
.my-slider {
  background-color: red;
}
</style>

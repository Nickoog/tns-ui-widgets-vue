<template>
  <StackLayout>
    <Progress 
      class="my-progress" 
      :value="myProgProp" 
      :maxValue="myMaxVal"
      @valueChange="onValueChange($event)"></Progress>
    <Button text="tap" @tap="onBtnTap($event)"></Button>
  </StackLayout>
</template>

<script lang="ts">
import { EventData } from 'tns-core-modules/data/observable/observable'
import { Progress } from 'tns-core-modules/ui/progress'
import { StackLayout } from 'tns-core-modules/ui/layouts/stack-layout'

export default {
  data() {
    return {
      myProgProp: 0,
      myMaxVal: 100,
    }
  },
  methods: {
    onValueChange(args: EventData) {
      const myControl = <Progress>args.object
      console.log('new value: ', myControl.value)
    },
    onBtnTap(args: EventData) {
      setInterval(() => {
        this.myProgProp = this.myProgProp + 1;            
      }, 300);
    }
  }
}
</script>

<style scoped>
.my-progress {
  color: green;
}
</style>

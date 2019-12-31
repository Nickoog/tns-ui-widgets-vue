<template>
  <StackLayout>
    <ActivityIndicator :busy="myActivityBusy"></ActivityIndicator>
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
      myActivityBusy: false
    }
  },
  methods: {
    onBtnTap(args: EventData) {
      this.myActivityBusy = !this.myActivityBusy
    }
  }
}
</script>

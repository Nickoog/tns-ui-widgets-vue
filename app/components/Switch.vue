<template>
  <StackLayout>
    <Switch class="my-switch" :checked="mySwitchChecked" @checkedChange="onCheckedChange($event)"></Switch>
    <Button text="tap" @tap="onBtnTap($event)"></Button>
  </StackLayout>
</template>

<script lang="ts">
import { EventData } from 'tns-core-modules/data/observable/observable'
import { Switch } from 'tns-core-modules/ui/switch'
import { StackLayout } from 'tns-core-modules/ui/layouts/stack-layout'

export default {
  data() {
    return {
      mySwitchChecked: true
    }
  },
  methods: {
    onCheckedChange(args: EventData) {
      const sw = <Switch>args.object
      console.log('new switch value: ', sw.checked)
    },
    onBtnTap(args: EventData) {
      this.mySwitchChecked = !this.mySwitchChecked
    }
  }
}
</script>

<style scoped>
.my-switch {
  background-color: red;
}
</style>


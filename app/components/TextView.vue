<template>
  <StackLayout>
    <StackLayout>
      <TextField v-model="firstName" editable="false"></TextField>
    </StackLayout>
    <button text="Tap" @onTap="onTap($event)"></button>

    <DatePicker @dateChange="onDateChanged($event)" @monthChange="onDateChanged($event)" @loaded="onDateLoaded($event)"></DatePicker@dateChange="onDateChanged">
  </StackLayout>
</template>

<script lang="ts">
import { EventData } from 'tns-core-modules/data/observable/observable'
import { DatePicker } from 'tns-core-modules/ui/date-picker'
import { StackLayout } from 'tns-core-modules/ui/layouts/stack-layout'

export default {
  data() {
    return {
      firstName: 'NIco'
    }
  },
  methods: {
    onTap(args: EventData) {
      alert('first name: ' + this.firstName)
    },
    onDateLoaded(args: EventData) {
      const datePicker = <DatePicker>args.object

      datePicker.year = 2015
      datePicker.month = 1
      datePicker.day = 20
    },
    onDateChanged(args) {
      console.log('old value: '+ args.oldValue)
      console.log('new value: '+ args.value)
    },
    monthChange(args) {
      console.log('old value: '+ args.oldValue)
      console.log('new value: '+ args.value)
    }
  }
}
</script>

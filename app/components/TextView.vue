<template>
  <StackLayout>
    <StackLayout>
      <TextField v-model="firstName" editable="false"></TextField>
    </StackLayout>
    <button text="Tap" @onTap="onTap($event)"></button>

    <TimePicker
      @loaded="onTimeLoaded($event)"
      @timeChange="onTimeChanged($event)"
    ></TimePicker>
    <DatePicker
      @dateChange="onDateChanged($event)"
      @monthChange="onDateChanged($event)"
      @loaded="onDateLoaded($event)"
    ></DatePicker>
    <ListPicker
      :items="myItems"
      :selectedIndex="selectedIndex"
      @selectedIndexChange="onSelectedIndexChange($event)"
    ></ListPicker>
  </StackLayout>
</template>

<script lang="ts">
import { EventData } from 'tns-core-modules/data/observable/observable'
import { DatePicker } from 'tns-core-modules/ui/date-picker'
import { TimePicker } from 'tns-core-modules/ui/time-picker'
import { ListPicker } from 'tns-core-modules/ui/list-picker'
import { StackLayout } from 'tns-core-modules/ui/layouts/stack-layout'

export default {
  data() {
    return {
      firstName: 'NIco',
      myItems: ['toto', 'tata', 'mimi', 'kiki'],
      selectedIndex: 2
    }
  },
  methods: {
    onTap(args: EventData) {
      alert('first name: ' + this.firstName)
    },
    onTimeLoaded(args: EventData) {
      const timePicker = <TimePicker>args.object

      timePicker.hour = 12
      timePicker.minute = 43
    },
    onTimeChanged(args) {
      console.log('old value: ' + args.oldValue)
      console.log('new value: ' + args.value)
    },
    onDateLoaded(args: EventData) {
      const datePicker = <DatePicker>args.object

      datePicker.year = 2015
      datePicker.month = 1
      datePicker.day = 20
    },
    onDateChanged(args) {
      console.log('old value: ' + args.oldValue)
      console.log('new value: ' + args.value)
    },
    monthChange(args) {
      console.log('old value: ' + args.oldValue)
      console.log('new value: ' + args.value)
    },
    onSelectedIndexChange(args) {
      const ListPicker = <ListPicker>args.object

      alert('name: ' + this.myItems[ListPicker.selectedIndex])
    }
  }
}
</script>

<template>
  <StackLayout>
    <StackLayout>
      <Label text="First Name"></Label>
      <TextField
        autocorrect="false"
        maxLength="10"
        v-model="firstName"
        hint="Enter your first name"
        @returnPress="onReturnPress($event)"
      ></TextField>
    </StackLayout>

    <StackLayout>
      <Label text="First Name"></Label>
      <TextField
        autocorrect="false"
        maxLength="10"
        v-model="firstName"
        hint="Enter your first name"
        @focus="onFocus($event)"
      ></TextField>
    </StackLayout>

    <button text="Submit" @tap="onSave($event)"></button>
  </StackLayout>
</template>

<script lang="ts">
import { EventData } from 'tns-core-modules/data/observable/observable'
import { TextField } from 'tns-core-modules/ui/text-field'
import { StackLayout } from 'tns-core-modules/ui/layouts/stack-layout'

export default {
  data() {
    return {
      firstName: 'NIco'
    }
  },
  methods: {
    onSave(args: EventData) {
      alert('first name: ' + this.firstName)
    },
    onReturnPress(args: EventData) {
      alert('return pressed')
    },
    onFocus(args: EventData) {
      alert('focused')
    }
  }
}
</script>

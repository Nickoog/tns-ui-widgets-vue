<template>
  <StackLayout>
    <StackLayout>
      <TextField v-model="firstName" editable="false"></TextField>
    </StackLayout>
    <button text="Tap" @onTap="onTap($event)"></button>
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
    onTap(args: EventData) {
      alert('first name: ' + this.firstName)
    }
  }
}
</script>

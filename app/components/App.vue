<template>
  <Page>
    <Switch />
  </Page>
</template>

<script lang="ts">
import Button from './Button'
import Label from './Label'
import Switch from './Switch'

export default {
  components: { Button, Label, Switch }
}
</script>

<style scoped>
ActionBar {
  background-color: #53ba82;
  color: #ffffff;
}

.message {
  vertical-align: center;
  text-align: center;
  font-size: 20;
  color: #333333;
}
</style>

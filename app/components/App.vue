<template>
  <Page>
    <Label />
  </Page>
</template>

<script lang="ts">
import Button from './Button'
import Label from './Label'

export default {
  components: { Button, Label }
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

<template>
  <Page>
    <Button />
  </Page>
</template>

<script lang="ts">
import Button from './Button'

export default {
  components: { Button }
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

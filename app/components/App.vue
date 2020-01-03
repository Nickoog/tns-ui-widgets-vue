<template>
  <Page>
    <SearchBar />
  </Page>
</template>

<script lang="ts">
import Button from './Button'
import Label from './Label'
import Switch from './Switch'
import Slider from './Slider'
import Progress from './Progress'
import ActivityIndicator from './ActivityIndicator'
import List from './List'
import TextField from './TextField'
import TextView from './TextView'
import SegmentedBar from './SegmentedBar'
import SearchBar from './SearchBar'

export default {
  components: {
    Button,
    Label,
    Switch,
    Slider,
    Progress,
    ActivityIndicator,
    List,
    TextField,
    TextView,
    SegmentedBar,
    SearchBar
  }
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

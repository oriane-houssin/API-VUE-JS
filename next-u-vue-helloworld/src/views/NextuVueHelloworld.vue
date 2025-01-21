<script lang="ts">
import { ref } from 'vue'

export default {
  name: 'NextuVueHelloworld',
  props:{
    count:{
        type: Number,
        default: 2
    },
  },
  setup(props) {
    const message = ref('Bonjour tout le monde')
    const countData = props.count
    return {
      message,
      countData
    }
  },
}
</script>
<template>
  <div>{{ message }}{{ countData }}</div>
</template>
<style></style>

<template>
<div class="view-home">
  <filterList></filterList>
</div>
</template>

<script>
import filterList from '@/views/Home/filterList'

export default {
  components: {
    filterList
  }
}
</script>

<style>
.view-home .filterList {
  position: relative;
  top:  -20px;
}
</style>

<template>
  <div class="clicks">
    <h4 class="clicks-text">Clicks: {{click}}</h4>
  </div>
</template>

<script>
export default {
  name: 'Clicks',
  props: ['click']
}
</script>

<style>
.clicks-text{
  font-size: 24px;
}
</style>
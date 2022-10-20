<template>
  <div class="asideWrapper">
    <calendarItem></calendarItem>
    <themeSelect></themeSelect>
  </div>
</template>

<script>
import calendarItemVue from './calendarItem.vue';
import themeSelectVue from './themeSelect.vue';

export default {
components: {
  calendarItem: calendarItemVue,
  themeSelect: themeSelectVue,
}
}
</script>

<style>
.asideWrapper {
    width: 25%;
    height: 100vh;
}

</style>
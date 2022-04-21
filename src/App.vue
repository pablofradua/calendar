<script setup>
import Day from "./components/Day.vue";
const logEvent = (dayStatus) =>{
  console.log(`${dayStatus.dayOfMonth} has been ${dayStatus.isSelected?'selected':'unselected'}`)
}
</script>
<template>
  <Day
    v-for="n in 31"
    :key="n"
    :dayOfMonth="n"
    @onselect="(dayStatus) =>logEvent(dayStatus)"
  />
</template>

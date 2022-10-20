<template>
  <div class="appMainWrapper">
    <inputComponent></inputComponent> 
    <selectDay></selectDay>
    <taskWrapper></taskWrapper>
  </div>
</template>

<script>
import inputComponentVue from './inputComponent.vue';
import selectDayVue from './selectDay.vue';
import tasksWrapperVue from './tasksWrapper.vue';

export default {
components: {
    inputComponent: inputComponentVue,
    selectDay: selectDayVue,
    taskWrapper: tasksWrapperVue
},
data () {
    return {
  
    }
}

}
</script>

<style scoped>
.appMainWrapper {
width: 53%;
height: 100vh;
}

</style>
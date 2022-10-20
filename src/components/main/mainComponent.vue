<template>
  <div class="appMainWrapper">
    <inputComponent
    v-on:addTodo="addTodo"
    ></inputComponent> 
    <selectDay></selectDay>
    <taskWrapper
    v-on:removeTodo="removeTodo"
    :titleTaskWrapper="titleTaskWrapper"
    :tasks="tasks"
    ></taskWrapper>
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
},
methods: {
removeTodo(task) {
  this.$emit('removeTodo',task)
},
addTodo(data) {
this.$emit('addTodo',data)
}
},
props: [
  'tasks',
  'titleTaskWrapper'
]

}
</script>

<style scoped>
.appMainWrapper {
width: 53%;
height: 100vh;
}

</style>
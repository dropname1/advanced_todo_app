<template>
  <div class="selectWrapper">

    <div class="selectItem day">Day:
      <span class="selectedData selectDay"
      @click="isCalendar = !isCalendar"
      >{{selectItems[0].title}}</span>
      <calendarItem 
      @selectDay="selectDay" 
      class="calendarItemClass" 
      v-if="isCalendar"
      >
    </calendarItem>
    </div>

    <div class="selectItem time">Time:
      <span class="selectedData selectTime"
      @click="isTime = !isTime"
      >{{selectItems[1].hour}}:{{selectItems[1].minut}}</span>
      <timeItem 
      v-if="isTime"
      v-on:addHour="addHour"
      v-on:addMinut="addMinut"
      >
      </timeItem>
    </div>

    <div class="selectItem tag">Tag:
      <span class="selectedData selectTag"
      @click="isTag = !isTag"
      >{{selectItems[2].title}}</span>
      <tagItem v-if="isTag"
      class="tagItemClass"
      >
      </tagItem>
    </div>

    <div class="selectItem category">Category:
      <span class="selectedData selectCategory"
      @click="isCategory = !isCategory"
      >{{selectItems[3].title}}</span>
      <categtoriesItem v-if="isCategory"
      class="categoriesItemClass"
      >
      </categtoriesItem>
    </div>

  </div>
</template>

<script>
import calendarItemVue from '../dataes elements/calendarItem.vue'
import categoriesItemVue from '../dataes elements/categoriesItem.vue'
import tagItemVue from '../dataes elements/tagItem.vue'
import timeItemVue from '../dataes elements/timeItem.vue'
export default {
data () {
  return {
    selectItems: [
      { id: 1, title: 'today'},
      { id: 2, hour: '07', minut: '10'},
      { id: 3, title: 'missing'},
      { id: 4, title: 'missing'},
    ],
    isCalendar : false,
    isTime: false,
    isTag: true,
    isCategory: true,
  }
},
components: {
  calendarItem: calendarItemVue,
  timeItem: timeItemVue,
  tagItem: tagItemVue,
  categtoriesItem: categoriesItemVue

},
methods: {
  selectDay (day) {
    this.selectItems[0].title = day.day
  },
  addHour (hour) {
    this.selectItems[1].hour = hour.time
  },
  addMinut (minut) {
    this.selectItems[1].minut = minut.time
  }
}
}
</script>

<style scoped>
.selectWrapper {
    margin: 0 auto;
    width: 86%;
    display: flex;
    justify-content: space-between;
    font-size: 16px;
    margin-top: 10px;
    color: gray;
}
.selectItem {
  display: flex;
}
.selectedData {
    display: block;
    color: white;
    font-size:15px;
    cursor: pointer;
    background:linear-gradient(#1c1e2b,#191b26,#191b26,#202230);
    padding-left: 4px;
    padding-right: 4px;
    padding-bottom: 2px;
    padding-top: 2px;
    border-radius: 6px;
    box-shadow: 1px 1px 5px rgb(14, 14, 14);
    width: fit-content;
    max-width: 90px;
    min-width: 53px;
    overflow: hidden;
    text-align: center;
}
.calendarItemClass {
  color: white;
  position: absolute;
  transform: scale(0.75);
  background: radial-gradient(rgb(32, 25, 25), black);
  top: 66px;
  margin-left: -76px;
  box-shadow: 2px 2px 10px black;
}
.tagItemClass {
  position: absolute;
  margin-top: 34px;
  box-shadow: 2px 2px 10px black;
}
.categoriesItemClass {
  position: absolute;
  margin-top: 34px;
  box-shadow: 2px 2px 10px black;
}
</style>
<template>
  <div class="timeItemWrapper">
    <div class="timeWrapper">
        <div class="hours">
            <div class="hour" :class="{selectedHour: hour.selected}" v-for="(hour, index ) in hours" :key="index"  @click="selectHour(hour)">{{hour.time}}</div>
        </div>
        <div class="minuts">
            <div class="minut" :class="{selectedMinut: minut.selected}" v-for="(minut, index) in minuts" :key="index" @click="selectMinut(minut)">{{minut.time}}</div>
        </div>
    </div>
  </div>
</template>

<script>
export default {
data () {
    return {
        hours: [
            { time: '05', selected: false }, { time: '06', selected: false }, { time: '07', selected: true }, 
            { time: '08', selected: false }, { time: '09', selected: false }, { time: '10', selected: false }, 
            { time: '11', selected: false }, { time: '12', selected: false }, { time: '13', selected: false },
            { time: '14', selected: false }, { time: '15', selected: false }, { time: '16', selected: false },
            { time: '17', selected: false }, { time: '18', selected: false }, { time: '19', selected: false }, 
            { time: '20', selected: false }, { time: '21', selected: false }, { time: '22', selected: false }, 
            { time: '23', selected: false }, { time: '00', selected: false }, { time: '01', selected: false }, 
            { time: '02', selected: false }, { time: '03', selected: false }, { time: '04', selected: false }
        ],
        minuts: [
            { time: '00', selected: false }, { time: '05', selected: false }, { time: '10', selected: true },
            { time: '15', selected: false }, { time: '20', selected: false }, { time: '25', selected: false },
            { time: '30', selected: false }, { time: '35', selected: false }, { time: '40', selected: false },
            { time: '45', selected: false }, { time: '50', selected: false }, { time: '55', selected: false },
            { time: '60', selected: false}
        ],
    }
},
methods: {
    selectHour (item) {
        this.hours.map(item => item.selected = false)
        item.selected = true
        this.$emit('addHour',item)

    },
    selectMinut (item) {
        this.minuts.map(item => item.selected = false)
        item.selected = true
        this.$emit('addMinut', item)

    }
}
}
</script>

<style scoped>
/* width */
::-webkit-scrollbar {
    width: 7px;
}

/* Track */
::-webkit-scrollbar-track {
    box-shadow: inset 0 0 5px grey;
    border-radius: 5px;
}

/* Handle */
::-webkit-scrollbar-thumb {
    background: rgba(161, 161, 153, 0.336);
    border-radius: 10px;
}
.timeWrapper {
    width: 90px;
    background: radial-gradient(#3d3d3d, #2d2d2d);
    overflow: hidden;
    height: 217px;
    display: flex;
    border-radius: 10px;
    border: 1px solid rgba(0, 0, 0, 0.363);
    position: absolute;
    margin-top: 34px;
    margin-left: -65px;
    box-shadow: 2px 2px 10px black;
}
.hours {
    overflow-y:scroll;
    width: 50%;
    color: black;
    text-align: center;
}
.minuts {
    overflow-y: scroll;
    width: 50%;
    color: rgba(0, 0, 0, 0.76);
    text-align: center;
}
.hour {
    cursor: pointer;
}
.minut {
    cursor: pointer;
}
.selectedHour, .selectedMinut {
    background-color: #ac1769;
    margin: 0px 4px;
    border-radius: 5px;
}
</style>
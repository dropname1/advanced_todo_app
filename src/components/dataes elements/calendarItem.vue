<template>
    <div class="calendarWrapper">
        <div class="mounthName">{{NowMounth}}</div>
        <div class="dateWrapper">
            <div class="daysOfWeek">
                <span class="dayOfWeek">Mo</span>
                <span class="dayOfWeek">Tu</span>
                <span class="dayOfWeek">We</span>
                <span class="dayOfWeek">Th</span>
                <span class="dayOfWeek">Fr</span>
                <span class="dayOfWeek">Sa</span>
                <span class="dayOfWeek">Su</span>
            </div>
            <div class="daysOfMounth">
                <div class="dayOfMounth" 
                v-for="dayItem in daysOfMounth" 
                :key="dayItem.id"
                :class="{selectedDay : dayItem.selected }"
                @click="selectDay(dayItem)"
                >
                    {{dayItem.day}}
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            NowMounth: '',
            NowYear: '',
            daysOfMounth: [],
            mounthNames: [
                { id: 1, name: "January", days: 31 },
                { id: 2, name: "February", days: 28 },
                { id: 3, name: "March", days: 31 },
                { id: 4, name: "April", days: 30 },
                { id: 5, name: "May", days: 31 },
                { id: 6, name: "June", days: 30 },
                { id: 7, name: "July", days: 31 },
                { id: 8, name: "August", days: 31 },
                { id: 9, name: "September", days: 30 },
                { id: 10, name: "October", days: 31 },
                { id: 11, name: "November", days: 30 },
                { id: 12, name: "December", days: 31 }
            ],

        }
    },
    methods: {
        selectDay(day) {
            this.daysOfMounth.map(item => {
                item.selected = false
            })
            day.selected = true
            this.$emit('selectDay',day)
        }
    },
    mounted() {
        const date = new Date()
        let mounthNumber = date.getMonth()
        let mounthDays = new Date(this.NowYear, mounthNumber, 0).getDate()
        this.NowYear = date.getFullYear()
        this.NowMounth = this.mounthNames[mounthNumber].name


        let year = this.NowYear;
        let month = mounthNumber;
        let day = new Date(year + "-" + month + "-01").getDay();
        day = day + 1

        while (day > 0) {
            this.daysOfMounth.push({ day: '', active: false, selected: null })
            day--
        }

        for (let i = 1; i <= mounthDays; i++) {
            this.daysOfMounth.push({ day: i, active: false, selected: null })
        }

    },
}
</script>

<style scoped>
.calendarWrapper {
    margin: 0 auto;
    margin-top: 20px;
    width: 280px;
    height: 290px;
    background-color: #2b2e38;
    border-radius: 15px;
    font-size: 16px;
}

.mounthName {
    width: fit-content;
    margin: 0 auto;
    padding-top: 20px;
    margin-bottom: 10px;
    font-size: 18px;
}

.dateWrapper {
    width: 90%;
    margin: 0 auto;
}

.daysOfWeek {
    display: flex;
    text-align: center;
}

.dayOfWeek {
    width: 36px;
    color: gray;
}

.daysOfMounth {
    margin-top: 10px;
    display: flex;
    flex-wrap: wrap;
    text-align: center;
    cursor: pointer;
    line-height: 35px;
}

.dayOfMounth {
    width: 36px;
    height: 36px;
}
.selectedDay {
    background-color: #9f1562;
    border-radius: 10px;
}
</style>
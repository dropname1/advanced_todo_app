<template>
    <div class="mainAppWrapper">
        <sideBar
        v-on:buttonPressed="buttonPressed"
        ></sideBar>
        <mainComponent
        :tasks="tasks"
        :titleTaskWrapper="titleTaskWrapper"
        v-on:removeTodo="removeTodo"
        v-on:addTodo="addTodo"
        ></mainComponent>
        <asideComponent></asideComponent>
    </div>
</template>

<script>
import asideComponentVue from './components/aside/asideComponent.vue';
import mainComponentVue from './components/main/mainComponent.vue';
import sideBarVue from './components/navigation/sideBar.vue';
export default {
data () {
    return {
        tasks: [
            {
                id: 1, 
                title: 'Test Todo 1', 
                completed: false, 
                checked: false, 
                completedTime: {
                    day: '',
                    mounth: '',
                    year: ''
                },
                date: {
                    day: '',
                    mounth: '',
                    year: ''
                },
                tag: 'missing',
                category: 'missing'
            },{
                id: 2, 
                title: 'Test Todo 2', 
                completed: false, 
                checked: false, 
                completedTime: {
                    day: '',
                    mounth: '',
                    year: ''
                },
                date: {
                    day: '',
                    mounth: '',
                    year: ''
                },
                tag: 'missing',
                category: 'missing'
            },{
                id: 3, 
                title: 'Test Todo 3', 
                completed: false, 
                checked: false, 
                completedTime: {
                    day: '',
                    mounth: '',
                    year: ''
                },
                date: {
                    day: '',
                    mounth: '',
                    year: ''
                },
                tag: 'missing',
                category: 'missing'
            }
        ],
        saveTasks: [],
        tasksToday: [],
        tasksWeek: [],
        progress: [],
        tags: [],
        titleTaskWrapper: 'all tasks',
        todoId: 1,
        maxDay: 0,
    }
},
components: {
    sideBar: sideBarVue,
    asideComponent: asideComponentVue,
    mainComponent: mainComponentVue,
},
methods: {
    removeTodo(task) {
        this.progress.push(task)
        this.tasks = this.tasks.filter(item => item !== task)  
        this.saveTasks = this.tasks
    },
    buttonPressed(name,title) {
        this.titleTaskWrapper = title
        this.dateFilterButton(name,title)
    },
    addTodo (data) {
        this.tasks.push({
            id: this.todoId++,
            title: data.title,
            completed: false,
            checked: false,
            completedTime: {
                day: '',
                mounth: '',
                year: ''
            },
            date: {
                day: data.day,
                mounth: data.mounth,
                year: data.year,
                week: data.week,
            },
            tag: 'missing',
            category: 'missing'
        })
        this.saveTasks = this.tasks
    },
    dateFilterButton (name,title) {
        let date = new Date()
        let day = date.getDate()
        let mounth = date.getMonth()
        let year = date.getFullYear()
        let week = date.getDay()


        if (name === 'All') {
            this.tasks = this.saveTasks
        } 
        else if (name === 'Today') {
            this.tasks = this.tasks.filter((item)=> {
                
                return (
                item.date.day === day && 
                item.date.mounth === mounth &&
                item.date.year === year)
            })
        }
        else if (name === 'Week') {
            this.tasks = this.tasks.filter((item)=> {
                return item.date.day <= item.date.day + 7 
            })
        }
    }


}
}
</script>

<style>
.mainAppWrapper {
    display: flex;
    width: 100%;
    height: 100vh;
    background-color: #191B26;
    color: white;
    font-family: monospace;
    overflow: hidden;
}
</style>

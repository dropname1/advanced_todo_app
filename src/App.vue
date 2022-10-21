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
                title: 'Test Todo 1: TODAY; Cat: missin2', 
                completed: false, 
                checked: false, 
                completedTime: {
                    day: '',
                    mounth: '',
                    year: ''
                },
                date: {
                    day: 21,
                    mounth: 9,
                    year: 2022,
                },
                tag: 'missing',
                category: 'missing2'
            },{
                id: 2, 
                title: 'Test Todo 2: WEEK; Tag: missing2', 
                completed: false, 
                checked: false, 
                completedTime: {
                    day: null,
                    mounth: null,
                    year: null
                },
                date: {
                    day: 24,
                    mounth: 9,
                    year: 2022
                },
                tag: 'missing2',
                category: 'missing'
            },{
                id: 3, 
                title: 'Test Todo 3: MOUNTH', 
                completed: false, 
                checked: false, 
                completedTime: {
                    day: null,
                    mounth: null,
                    year: null,
                },
                date: {
                    day: 29,
                    mounth: 9,
                    year: 2022
                },
                tag: 'missing',
                category: 'missing'
            }
        ],
        // goals: [{
        //     id: 1, title: 
        //     'Leran Js', 
        //     completed: false, 
        //     checked: false, 
        //     date: {
        //         day: null, 
        //         month: null,
        //         year: null
        //     },
        //     completedTime: {
        //         day: null,
        //         month: null,
        //         year: null
        //     },
        //     coalTime: {
        //         day: null,
        //         month: null,
        //         year: null
        //     }
        // }
        // ],
        allTasks: [],
        progress: [],
        categories: [],
        tags: [],
        progress: [],
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
        this.allTasks = this.tasks
    },
    buttonPressed(name,title) {
        this.titleTaskWrapper = title
        name === 'All' ||
        name === 'Today'||
        name === 'Week' ? this.dateFilter(name): null;

        name === 'Categories' ? this.categoriesFilter('missing2'): null; // parametr
        name === 'Tags' ? this.tagsFilter('missing2') : null; // parametr
        name === 'Progress' ?  this.progressFiler(): null;
        name === 'Setting' ?  this.setting(): null;
    },
    addTodo (data) {
        this.clearState()
        this.tasks.push({
            id: this.todoId++,
            title: data.title,
            completed: false,
            checked: false,
            completedTime: {
                day: null,
                mounth: null,
                year: null
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
        this.allTasks = this.tasks
    },
    dateFilter (name) {
        this.clearState()
        let date = new Date()
        let day = date.getDate()
        let mounth = date.getMonth()
        let year = date.getFullYear()


        if (name === 'All') {
            this.tasks = this.allTasks
        } 
        if (name === 'Today') {
            this.tasks = this.allTasks
            this.tasks = this.tasks.filter((item)=> {
                return (
                    item.date.day === day && 
                    item.date.mounth === mounth && 
                    item.date.year === year)
            })
        }
        if (name === 'Week') {
            this.tasks = this.allTasks
            this.tasks = this.tasks.filter((item)=> {
                if (item.date.mounth === mounth) {
                   return item.date.day <= day + 7
                } 
            })
            
        }
    },
    categoriesFilter (category) {
        this.clearState()
        this.tasks = this.allTasks

        this.tasks = this.tasks.filter((item)=> {
            return item.category === category
        })
        this.$store.state.isCategory = true
    },
    tagsFilter(tag) {
        this.clearState()
        this.tasks = this.allTasks

        this.tasks = this.tasks.filter((item)=> {
            return item.tag === tag
        })
        this.$store.state.isTags = true
    },
    progressFiler () {
        this.clearState()
        this.tasks = this.allTasks
        this.tasks = this.progress.filter((item)=> {
            return (item.completed === true)
        })
        this.$store.state.isProgress = true
    },
    setting () {
        this.clearState()
        this.tasks = []
        console.log('Your open Setting')
        this.$store.state.isSetting = true
    },
    clearState () {
        this.$store.state.isSetting = false
        this.$store.state.isCategory = false
        this.$store.state.isTags = false
        this.$store.state.isProgress = false
    }



},
mounted () {
    this.allTasks = this.tasks
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

<template>
<div class="sideBarWrapper">
    <div class="buttonsWrapper" v-for="(button, index) in buttons" :key="button.id">
        <sideButton
        :button="buttons[index]"
        :buttonsArray="buttons"

        v-on:buttonPressed="buttonPressed"
        ></sideButton>
    </div> 
    <div>
    </div>
</div>
</template>

<script>
import sideButtonVue from './sideButton.vue'
export default {
data() {
    return {
        buttons: [
            { id: 1, pressed: false, title:'all tasks',name: 'All'},
            { id: 2, pressed: false, title:'today\'s tasks',name: 'Today'},
            { id: 3, pressed: false, title:'tasks for the week',name: 'Next 7 days'},
            { id: 4, pressed: false, title: 'categories', name: 'Categories'},
            { id: 5, pressed: false, title:'tags',name: 'Tags'},
            { id: 6, pressed: false, title:'goals',name: 'Goal'},
            { id: 7, pressed: false, title:'progress',name: 'Progress'},
            { id: 8, pressed: false, title:'setting',name: 'Setting'},
        ],
    }
},
components: {
    sideButton: sideButtonVue,
},
methods: {
    buttonPressed(name, title) {
        this.$emit('buttonPressed',name,title)
    }
},
props:[
]
}
</script>

<style scoped>
.sideBarWrapper {
    margin-top: 20px;
    width: 22%;
    height: 100vh;
}
</style>
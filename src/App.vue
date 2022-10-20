<template>
    <div class="mainAppWrapper">
        <sideBar></sideBar>
        <mainComponent></mainComponent>
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
    }
},
components: {
    sideBar: sideBarVue,
    asideComponent: asideComponentVue,
    mainComponent: mainComponentVue,
},
methods: {
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

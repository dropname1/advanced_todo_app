<template>
    <div class="sideBarButton"
    @click="buttonPressed(button.name, button.title)"
    >
    {{button.name}}
    </div>
</template>

<script>
export default {
data () {
  return {
    
  }
},
methods: {
buttonPressed(name, title) {
  this.$emit('buttonPressed',name, title)
}
},
props: [
  'button'
]
}
</script>

<style scoped>
.sideBarButton {
  padding: 11px 20px;
  background-color: #2B2E38;
  margin-top: 8px;
  border-radius: 8px;
  font-size: 16px;
  margin-left: 33px;
  margin-right: 33px;
  cursor: pointer;
  transition: 0.2s;
  box-shadow: 1px 1px 5px rgb(14, 14, 14);
}
.sideBarButton:hover {
  transform: translate(8px);
  transition: 0.3s;
}
.pressed {
  transform: translate(8px);
}
</style>
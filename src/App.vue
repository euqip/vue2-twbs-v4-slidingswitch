<template lang="pug">
  #app
    img(src="./assets/logo.png")
    h2 {{ msg }}
    .container
      .row
        div On sait depuis longtemps que travailler avec du texte lisible et contenant ....
        toggleSwitch(name="switch1" :value="true" :stylecl="false"  texton="ON" textoff="OFF")
        div On sait depuis longtemps que travailler avec du texte lisible et contenant du sens est source ....

</template>

<script>
import toggleSwitch from './components/toggleswitch/toggle-switch'
export default {
  name: 'app',
  data () {
    return {
      msg: 'Welcome to Vue.js Toggleswitch sample with font Awesome 4.7 & TWBS V4'
    }
  },
  components: {
    toggleSwitch
  }

}
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

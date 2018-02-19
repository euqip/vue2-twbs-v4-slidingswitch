<template lang="pug">
  div
    input(type="hidden" :name = "name" :value="switchcursor")
    .toggleswitch(@click="togglevalue" :style= "{color: textfg}" )
      span.switchbutton.border(:class= "classtextbg" :style ="{backgroundColor: textbg}")
      span.cursor(
        :texton="texton"
        :textoff="textoff"
        :class="cursorposition"
        :style ="{backgroundColor: buttonbg, color: buttonfg}"
        )
</template>

<script>
  export default {
    name: "toggleSwitch",
    mixins: [
    ],
    extends: {
    },
    props: {
      "name"        : {type: String, default : ''}, // input field name
      "buttonbg"    : {type: String, default : ''}, // sliding button background color
      "buttonfg"    : {type: String, default : ''}, // sliding button foreground color
      "texton"      : {type: String, default : ''}, // text displyed when true (ON)
      "textonbg"    : {type: String, default : ''}, // text ON background color
      "textonfg"    : {type: String, default : ''}, // text ON foreground color
      "textoff"     : {type: String, default : ''}, // text displayed when false (OFF)
      "textoffbg"   : {type: String, default : ''}, // text OFF background color
      "textofffg"   : {type: String, default : ''}, // text OFF foreground color
      "value"       : {type: Boolean, default: false}, // slider switch initial value
      "rounded"     : {type: Boolean, default: true}, // rounded borders when true
      "borders"     : {type: Boolean, default: true}, // show borders when true
      "stylecl"     : {type: Boolean, default: true}, // style slider with classes like twbs v4 classes or ...
      "twbuttonbg" : {type: String, default : 'bg-secondary'}, // sliding button background color class
      "twbuttonfg" : {type: String, default : ''}, // sliding button foreground color class
      "twtextonbg" : {type: String, default : 'bg-primary'}, // text ON  background color class
      "twtextonfg" : {type: String, default : ''}, // text ON foreground color class
      "twtextoffbg": {type: String, default : 'bg-danger'}, // text OFF  background color class
      "twtextofffg": {type: String, default : ''}, // text OFF foreground color class

      }, //Alphabetized for better readability
    data () {
      return{
        switchcursor: false,
        textbg: "",
        textfg: "",
        cursorposition: "",
        round: '',
        foregroungcolor : '',
        classtextbg: ''
      }
    },

    computed: {
    },
    components: {},
    watch: {},
    methods: {
      togglevalue: function () {
        this.switchcursor= !this.switchcursor
        this.togglestyle()
      },
      togglestyle: function () {
        this.textbg= this.switchcursor ? this.textonbg : this.textoffbg
        this.textfg= this.switchcursor ? this.textonfg : this.textofffg
        this.round = this.rounded ? 'round' : ''
        this.classtextbg= (this.switchcursor ? this.twtextonbg : this.twtextoffbg) + " " + this.round
        this.cursorposition = (this.switchcursor ? "right" :"left") + " " + this.round

      }
    },
    // component life cycle hooks, use kebab-cased-names
      beforeCreate () {},
      mounted () {
        //set initial value from parent
        this.switchcursor= this.value
        this.togglestyle()
      },
  }
</script>

<style scoped lang="scss">
  $baseunit: 1.5rem;
  $duration: 0.3s;
  .toggleswitch{
    position : relative;
    display:inline-block;
    width : 2.5 * $baseunit;
    height : $baseunit;
    color: black;
    overflow: hidden;
  }
  .border{
    border: 1px solid rgba(0, 0, 0, 0.315);
  }

  .switchbutton.round{
  border-radius: 0.5 * $baseunit

  }

  .switchbutton {
  position: absolute;
  cursor: pointer;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  transition: $duration;
  overflow: hidden;
}

.cursor{
  position: absolute;
  content: "";
  height: 0.8* $baseunit;
  width: 0.8* $baseunit;
  left: 0.1* $baseunit;
  bottom: 0.1* $baseunit;
  background-color: grey;
  transition: $duration;
  font-size: 70%;
}
.cursor.right{
    left: 1.6 * $baseunit;
}
.cursor.right:before{
  position : absolute;
  left: -1 * $baseunit;
  content: attr(texton);
}
.cursor.left:after{
  position : absolute;
  left: 1 * $baseunit;
  content: attr(textoff);
}

.cursor.round{
  border-radius: 0.4 * $baseunit
}


</style>

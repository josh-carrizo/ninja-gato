<template>
<div class="row">

  <div class=" boton1">
    <div id="btn" @click="mostrar_perro()"><span class="noselect" >Perro</span><div id="circle"></div></div>
  </div>

  <div class="titulo">
    <h2 href="#" target="_blank">Ninja vs Perro</h2>
  </div>

  <div class=" boton2">
    <div id="btn" @click="mostrar_ninja()"><span class="noselect" >Ninja</span><div id="circle"></div></div>
  </div>

  <img :src="require(`../assets/${nombre}.gif`)" id="imagen">

</div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data() {
    return{
      nombre: "ninja"
    }
  },
  methods: {
    mostrar_ninja() {
      this.nombre = "ninja";
    },
    mostrar_perro() {
      this.nombre = "perro";
    }
  },
  beforeUpdate() {
    alert('Haz cambiado de opción')
  }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@keyframes tipsy {
  0 {
    transform: translateX(-50%) translateY(-50%) rotate(0deg);
  }
  100% {
    transform: translateX(-50%) translateY(-50%) rotate(360deg);
  }
}
html {
  height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: #2d3436;
  background-image: linear-gradient(315deg, #2d3436 0%, #000000 74%);
}
.boton1{
  position: absolute;
  top: 21%;
  right:10%;
}
.boton2{
  position: absolute;
  top: 21%;
  left:10%;

}
#btn {
  background: #222;
  height: 50px;
  min-width: 18rem;
  border: none;
  border-radius: 10px;
  color: #eee;
  font-size: 40px;
  font-family: 'Cookie', cursive;
  position: relative;
  transition: 1s;
  -webkit-tap-highlight-color: transparent;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  padding-top: 5px;
}

#btn #circle {
  width: 5px;
  height: 5px;
  background: transparent;
  border-radius: 50%;
  position: absolute;
  top: 0;
  left: 50%;
  overflow: hidden;
  transition: 500ms;
}

.noselect {
  -webkit-touch-callout: none;
    -webkit-user-select: none;
     -khtml-user-select: none;
       -moz-user-select: none;
        -ms-user-select: none;
            user-select: none;
}

#btn:hover {
  background: transparent;
}

#btn:hover #circle {
  height: 50px;
  width: 120px;
  left: 5.3rem;
  border-radius: 0;
  border-bottom: 1.5px solid #eee;
}
h2 {
  color: #fffbf1;
  text-shadow: 0 20px 25px #2e2e31, 0 40px 60px #2e2e31;
  font-size: 80px;
  font-weight: bold;
  text-decoration: none;
  letter-spacing: -3px;
  margin: 0;
  position: absolute;
  top: 65%;
  left:50%;

  transform: translateX(-50%) translateY(-50%);
}

h2:before,
h2:after {
  content: '';
  padding: .9em .4em;
  position: absolute;
  left: 50%;
  width: 100%;
  top: 50%;
  display: block;
  border: 15px solid  black;
  transform: translateX(-50%) translateY(-50%) rotate(0deg);
  animation: 10s infinite alternate ease-in-out tipsy;
}

h2:before {
  border-color: black black rgba(0, 0, 0, 0) rgba(0, 0, 0, 0);
  z-index: -1;
}

h2:after {
  border-color: rgba(0, 0, 0, 0) rgba(0, 0, 0, 0) black black;
  box-shadow: 25px 25px 25px rgba(46, 46, 49, .8);
}

#imagen{
  position:absolute;
  width: 25rem;
  height: 25rem;
  top:0;
  left:38%;
}
</style>

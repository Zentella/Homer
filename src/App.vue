<template>
  <div id="app">
    <span>{{ message }}</span>
    <img
      src="https://i.pinimg.com/originals/54/67/54/5467549d4d0c67f326e792d5803
bcc16.png"
    />
    <!--   envia datos de padre a hijo -->
<HelloVue @clickedResponse="clickChild" message="Ustedes son mis hijos..."></HelloVue>
<!--   <HelloVue message="Ustedes son mis hijos..."></HelloVue> -->
<!--   recibe datos  del hijo -->
<span class="response"> {{childResponse}}</span>    
<!--   <span class="response"> {{this.childResponse}} no poner this porque es global</span> -->

  </div>
</template>

<script>
import HelloVue from "./HelloVue.vue";

export default {
  name: "app",
  components: { HelloVue },
  data() {
    return {
      message: "Hola soy Homero",
      childResponse: ''
    };
  },
  methods: {
clickChild(childValue) {
this.childResponse = childValue;
}
}
};
</script>

<style scoped>
#app {
  display: flex;
flex-flow: column nowrap;
  font-size: 38px;
  font-family: "Calibri", sans-serif;
  color: darkblue;
  background: lightblue;
}
img {
  width: 25%;
  height: 25%;
}
.response {
color: red;
}

</style>
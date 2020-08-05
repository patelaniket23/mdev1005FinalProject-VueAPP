<template>
  <div class="home-component">

    <div class="jumbotron jumbotron-fluid">
        <div class="container">
          <img alt="Vue logo" src="https://9to5mac.com/wp-content/uploads/sites/6/2019/09/apple-tag.png?w=1600" width="100px">
          <h3 class="display-5 "><span style="color:red">Click Buy! - Just a click away to buy your products</span></h3>
          <p class="lead"><span style="color:red">This is my first Online Shopping Application using Vue.js.</span></p>
        </div>
    </div>
    <router-link to="/products" tag="button" class="btn buttonGreen-outline"><span style="color:black">Have a look at our products</span ></router-link>

  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
export default {
  name: 'home',
  components: {
    HelloWorld
  }
}
</script>
<style>
@import url('https://fonts.googleapis.com/css2?family=Krona+One&display=swap');
.jumbotron {
  padding: 1rem 0rem;
  font-family: 'Krona One', sans-serif;
}
h3, .display-5 {
  color: red;
}
.lead{
font-family: 'Krona One', sans-serif;
}
button{
  font-family: 'Krona One', sans-serif;
}
button:hover {
  color: black;
  background-color: red;
}
</style>

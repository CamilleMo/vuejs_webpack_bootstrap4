<template>
  <div class="hello">
          <div class="container">
        <!-- Example row of columns -->
            <div class="row">
              <div class="col-md-12">
              <h1 class="text-center">{{ msg }}</h1>
              <div class="card">
                  <div class="card-header">
                    Featured
                  </div>
                  <div class="card-body">
                    <h4 class="card-title">Special title treatment</h4>
                    <p class="card-text">With supporting text below as a natural lead-in to additional content.</p>
                    <router-link class="btn btn-primary" v-bind:to="'about'">About</router-link>
                  </div>
                </div>
     
              </div>
            </div>
          </div>
    </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>

<template>
    <div class="container">
      <br>
        <br>
      <div class="row">
              <div class="col-md-12">
              <h1 class="text-center">{{ msg }}</h1>
              <br>
              <div class="card">
                  <div class="card-header">
                    This page will show how to fetch an API
                  </div>
                  <div class="card-body">
                    <h4 class="card-title">Download a TODO list</h4>
                    <p class="card-text">If you don't want to, you can always return Home !</p>
                    <router-link class="btn btn-primary" v-bind:to="'/'">Home</router-link>
                  </div>
                </div>
     
              </div>
            </div>
          </div>

</template>

<script>
export default {
  name: 'About',
  data () {
    return {
      msg: 'This is the about page !'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: bold;
}
</style>

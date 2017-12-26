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
                    This page will show some basic Vue.js
                  </div>
                  <div class="card-body">
                    <h4 class="card-title">Click to display the User Form</h4>
                    <p class="card-text">If you don't want to, you can always return Home !</p>
                    <router-link class="btn btn-primary" v-bind:to="'/'">Home</router-link>
                    <br>
                    <br>
                    <button class="btn btn-primary" role="button">Show User Form</button>
                  </div>
                </div>
                <br>
                <div v-if="show_form" class="text-center">
                  <i class="fa fa-spinner fa-spin fa-5x fa-fw"></i>
                  <span class="sr-only">Loading...</span>
                </div>
                <br>
                <br>

                  <div class="form-group row" v-if="show_form">
                    <label for="example-text-input" class="col-2 col-form-label">Username</label>
                    <div class="col-10">
                      <input class="form-control" type="text" value="Please, enter your Username..." id="example-text-input">
                    </div>
                  </div>

                
            </div>
          </div>
        </div>

</template>

<script>
var Vue = require('vue');
export default {
  name: 'Basic',
  data () {
    return {
      msg: 'Vue is great !',
      show_form: true
    }
  },
  methods: {
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: bold;
}
</style>

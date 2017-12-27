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
                    <br>
                    <br>
                    <button class="btn btn-primary" v-on:click="fetch_api">Fetch API</button>
                  </div>
                </div>
                  <div v-if="loading" class="text-center">
                    <br>
                    <i class="fa fa-spinner fa-spin fa-5x fa-fw"></i>
                    <span class="sr-only">Loading...</span>
                  </div>
                   <div v-if="remote">
                    <br>
                    The result :
                    <table class="table table-sm table-hover">
                      <thead>
                        <tr>
                          <th>UserID</th>
                          <th>ID</th>
                          <th>Title</th>
                          <th>Completed</th>
                        </tr>
                      </thead>
                      <tbody>

                        <tr v-for="todo in todos">
                          <!-- <th scope="row">1</th> -->
                          <td>{{ todo.userId }}</td>
                          <td>{{ todo.id }}</td>
                          <td>{{ todo.title }}</td>
                          <td>{{ todo.completed }}</td>
                        </tr>

                      </tbody>
                      </table>

                  </div>
              </div>
            </div>
          </div>

</template>

<script>
var Vue = require('vue');
export default {
  name: 'About',
  data () {
    return {
      msg: 'This is the about page !',
      remote: false,
      loading:false,
      todos: {
            }
    }
  },
  methods: {
  fetch_api: function(){
    this.loading = true;
    var _this = this;

    fetch("http://jsonplaceholder.typicode.com/todos").then(function (response) {
            return response.json();
              }).then((result) => {
                  
                  this.todos_raw =  result;
                  //alert(result);
                  // this.todos = [];
                  var i;
                  for (i = 0; i < this.todos_raw.length; i++) {
                    _this.$set(this.todos, i, this.todos_raw[i]);
                  };
                  this.loading = false;
                  this.remote = true;
              });
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

<template>
  <NavBar />
  <router-view> </router-view>
</template>

<script>
import NavBar from './components/NavBar.vue'
import "bootstrap/dist/css/bootstrap.min.css"
import "bootstrap/dist/js/bootstrap"
import $ from 'jquery'

export default {
  components: {
    NavBar
  },
  setup() {
    $.ajax({
      url: "http://localhost:3000/user/account/token/",
      type: "post",
      data: {
        username: "ljq",
        password: "pljq",
      },
      success(resp) {
        console.log(resp);
      },
      error(resp) {
        console.log(resp);
      }
    })

    $.ajax({
      url: "http://localhost:3000/user/account/info/",
      type: "get",
      headers: {
        Authorization: "Bearer " + "eyJhbGciOiJIUzI1NiJ9.eyJqdGkiOiJlNzU4NGI2NDE5OTE0OWY0OGViZmMyNTkzZDExMTRkMSIsInN1YiI6IjIiLCJpc3MiOiJzZyIsImlhdCI6MTcxMzI3OTQ3MCwiZXhwIjoxNzE0NDg5MDcwfQ.OudRlvQGtcmQ7Q6qFQWYObqxAMalEI7NAbqBcF4DpGA"
      },
      success(resp) {
        console.log(resp);
      },
      error(resp) {
        console.log(resp);
      }
    })

    $.ajax({
      url: "http://localhost:3000/user/account/register/",
      type: "post",
      data: {
        username: "ljq",
        password: "pljq",
        confirmedPassword:"pljq"
      },
      success(resp) {
        console.log(resp);
      },
      error(resp) {
        console.log(resp);
      }
    })
  }

}
</script>


<style>
body {
  background-image: url('./assets/background3.jpg');
  background-size: 100%;
}
</style>

<template>
  <main class="login-form">
    <div class="container">
      <div class="row justify-content-center">
        <div class="col-md-8">
          <div class="card">
            <div class="card-header">Register</div>
            <div class="card-body">
              <div class="form-group row">
                <label for="email_address" class="col-md-4 col-form-label text-md-right"
                  >E-Mail Address</label
                >
                <div class="col-md-6">
                  <input
                    type="text"
                    id="email_address"
                    class="form-control"
                    name="email-address"
                    required
                    autofocus
                  />
                </div>
              </div>

              <div class="form-group row">
                <label for="password" class="col-md-4 col-form-label text-md-right">Password</label>
                <div class="col-md-6">
                  <input
                    type="password"
                    id="password"
                    class="form-control"
                    name="password"
                    required
                  />
                </div>
              </div>

              <div class="form-group row">
                <div class="col-md-6 offset-md-4">
                  <div class="checkbox">
                    <label> <input type="checkbox" name="remember" /> Remember Me </label>
                  </div>
                </div>
              </div>

              <div class="col-md-6 offset-md-4">
                <button @click="login" class="btn btn-primary">Register</button>
                <a href="#" class="btn btn-link"> Forgot Your Password? </a>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>
<script>
import axios from 'axios'
export default {
  methods: {
    login() {
      axios.get('http://localhost:3000/login').then((response) => {
        console.log(response)
        if (response.data.message === 'login exitoso') {
          window.location.href = '/'
        }
      })
    }
  }
}
</script>

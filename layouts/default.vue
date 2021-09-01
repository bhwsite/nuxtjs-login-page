<template>
  <no-ssr>
    <div>
      <section class="hero is-primary" v-if="isLoggedIn">

        <div class>
          <nav class="navbar" role="navigation" aria-label="main navigation">
            <div class="navbar-brand">
              <a class="navbar-item" href="/">
                <img src="~/assets/car.jpg">
              </a>
            </div>

            <div class="navbar-menu">
              <div class="navbar-start">
                <a href="/" class="navbar-item">Home</a>
                <a href="/user" class="navbar-item">User Management</a>
              </div>

              <div class="navbar-end">
                <div class="navbar-item">
                  <div class="buttons">
                    <a class="button is-light" @click="handleLogOut">Log out</a>
                  </div>
                </div>
              </div>

            </div>
          </nav>
        </div>
      </section>
      <nuxt/>
    </div>
  </no-ssr>
</template>

<script>
export default {
  computed: {
    isLoggedIn() {
      return this.$store.getters.isLoggedIn;
    }
  },
  methods: {
    handleLogOut() {
      this.$store.dispatch("logOut");
    }
  }
};
</script>

<style>
html {
  font-family: "sans-serif";
  font-size: 20px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

*,
*:before,
*:after {
  box-sizing: border-box;
  margin: 0;
}

.button--green {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #3b8070;
  color: #3b8070;
  text-decoration: none;
  padding: 10px 30px;
}

.button--green:hover {
  color: #fff;
  background-color: #3b8070;
}

.button--grey {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #35495e;
  color: #35495e;
  text-decoration: none;
  padding: 10px 30px;
  margin-left: 15px;
}

.button--grey:hover {
  color: #fff;
  background-color: #35495e;
}
</style>

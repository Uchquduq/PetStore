<template>
  <div>
    <nav class="navbar navbar-expand-lg navbar-dark bg-primary">
      <a class="navbar-brand" href="#"><router-link :to="{ name: 'iMain' }">
            {{ sitename }}
          </router-link></a>
      <button
        class="navbar-toggler"
        type="button"
        data-toggle="collapse"
        data-target="#navbarSupportedContent"
        aria-controls="navbarSupportedContent"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>

      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav mr-auto">
          <li class="nav-item">
            <a class="nav-link" href="#"
              >Home <span class="sr-only">(current)</span></a
            >
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">Link</a>
          </li>
        </ul>
        <form class="form-inline">
          <input
            class="form-control mr-sm-2"
            type="search"
            placeholder="Search"
            aria-label="Search"
          />
          <button class="btn btn-outline-light my-2 my-sm-0" type="submit">
            Search
          </button>
        </form>
        <router-link
          active-class="active"
          type="button"
          class="btn btn-outline-light my-2 my-sm-0 ml-2"
          :to="{ name: 'Form' }"
        >Checkout {{ cartItemCount }}

        </router-link>
      </div>
    </nav>
  </div>
</template>

<script>
export default {
  name: "my-header",
  data() {
    return {
      sitename: "WebStore"
    };
  },
  props: ["cartItemCount"],
  methods: {
    showCheckout() {
      this.$router.push({ name: "Form" });
    }
  }
};
</script>

<style scoped>
a {
  text-decoration: none;
  color: rgb(255 255 255 / 50%);
}
.router-link-exact-active {
  color: white;
}
</style>

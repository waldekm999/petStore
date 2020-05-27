<template>
  <header>
    <div class="navbar navbar-default">
      <div class="navbar-header">
        <h1>
          <router-link :to="{name: 'iMain'}">
            {{ sitename }}
          </router-link>
        </h1>
      </div>

      <div class="nav navbar-nav navbar-right cart">
        <router-link active-class="active" tag="button" class="btn btn-default btn-lg" :to="{name: 'Form'}">
    	    <i class="fas fa-cart-arrow-down"><span>{{ cartItemCount }}</span></i>
                        <p>Do kasy</p>
        </router-link>
      </div>
    </div>
  </header>
</template>

<script>
  export default {
    name: 'my-header',
    data () {
      return {
        sitename: "Skład dla zwierzaków :: Vue.js",
      }
    },
    props: ['cartItemCount'],
    methods: {
      showCheckout() {
        this.$router.push({name: 'Form'});
      }
    }
  }
</script>

<!-- Dodaj atrybut "scoped", by ograniczyć zasięg stylów CSS 
     do tylko tego komponentu. -->
<style scoped>
  a {
    text-decoration: none;
    color: black;
  }
</style>
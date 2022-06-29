<template>
  <div>    
    <nav class="navbar" role="navigation" aria-label="main navigation">
      <div class="navbar-brand">
        <a class="navbar-item" href="https://bulma.io">
          <img src="./assets/logo.png">
        </a>
      </div>

      <div id="navbarBasicExample" class="navbar-menu">
        <div class="navbar-start">
          <a class="navbar-item">
            {{home}}
          </a>

          <a class="navbar-item">
            Documentation
          </a>

          <div class="navbar-item has-dropdown is-hoverable">
            <a class="navbar-link">
              More
            </a>

            <div class="navbar-dropdown">
              <a class="navbar-item">
                About
              </a>
              <a class="navbar-item">
                Jobs
              </a>
              <a class="navbar-item">
                Contact
              </a>
              <hr class="navbar-divider">
              <a class="navbar-item">
                Report an issue
              </a>
            </div>
          </div>
        </div>

        <div class="navbar-end">
          <div class="navbar-item">
            <div class="buttons">
              <a class="button is-primary">
                <strong>Sign up</strong>
              </a>
              <a class="button is-light">
                Log in
              </a>
            </div>
          </div>
        </div>
      </div>
    </nav>


    <div class="section">
      <div class="columns">
        <div class="column is-3" v-for="product in products" :key="product.id">

          <div class="card">
            <div class="card-image">
              <figure class="image is-square">
                <img :src="product.src" :alt="product.name">
              </figure>
            </div>
            <div class="card-content">
              <div class="media">
                <div class="media-left">
                  <figure class="image is-48x48">
                    <img :src="product.src" :alt="product.name">
                  </figure>
                </div>
                <div class="media-content">
                  <p class="title is-4">{{product.name}}</p>
                  <p v-if="product.inventory > 10" class="subtitle is-6 tag is-success">Disponibile</p>
                  <p v-else-if="product.inventory > 0 && product.inventory <= 10" class="subtitle is-6 tag is-warning">Quasi esaurito</p>
                  <p v-else class="subtitle is-6 tag is-danger">Non disponibile</p>
                  <br>
                  <p class="subtitle is-6">{{product.price}}€</p>
                </div>
              </div>

              <div class="content">
                {{product.description}} 
                <a>@bulmaio</a>.
                <a href="#">#css</a> <a href="#">#responsive</a>
              </div>
            </div>
          </div> 

        </div>
      </div>
    </div>


  </div>
</template>

<script>
require('@/assets/main.scss');
export default {
  name: 'App',
  components: {
    
  },
  data(){
    return {
      home: "Home",
      
      products: [

        {
          id: 1,
          src: require("./assets/bag.png"),
          name: "Bag",
          price: "40",
          inventory: 12,
          description: "Best Bag"

        },
        {
          id: 2,
          src: require("./assets/glasses.png"),
          name: "Glasses",
          price: "120",
          inventory: 11,
          description: "Best Glass"

        },
        {
          id: 3,
          src: require("./assets/shoe.png"),
          name: "Glasses",
          price: "54",
          inventory: 0,
          description: "Best Shoes"

        },
        {
          id: 4,
          src: require("./assets/watch.png"),
          name: "Glasses",
          price: "254",
          inventory: 2,
          description: "Best Watch"

        },
      ]
    }
  }
}
</script>

<style lang="scss">

</style>

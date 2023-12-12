<template>
 <div class="dropdown">
  <button class="btn btn-secondary dropdown-toggle" type="button" data-bs-toggle="dropdown" aria-expanded="false">
  All products
  </button>
  <ul class="dropdown-menu">
    <li><button class="dropdown-item" type="button">Beef bobotie with yellow rice </button></li>
    <li><button class="dropdown-item" type="button">spaghetti Bolognese</button></li>
    <li><button class="dropdown-item" type="button">Italian Mince Meatball</button></li>
    <li><button class="dropdown-item" type="button">Rosemary chicken & Rice</button></li>
  </ul>
</div>
<div class="wrapper">
  <div class="container">
    
    <input type="text" id="data-search" placeholder="Enter your search" data-input>
    
  </div>
    <div class="row" v-if="products.length">
      <div class="prodCard" v-for="product in products" :key="product.id">
        <div class="header">
          <h3>{{ product.name }}</h3>

        </div>
        <div class="card-body">
          <img  :src="product.img" class="image" :alt="product.prodName" loading="lazy">
          <p :class="product.price > 78 ? 'expensive' :'cheap '" >R{{ product.price.toFixed(2) }}</p>
        </div>
        <div class="card-footer">
          <button  class="btn">view more</button>

        </div>
      </div>

    </div>
    <div v-else>
      <h2>Please try again later.</h2>
   </div>
</div>
</template>

<script>


export default {
  name: 'App',
 data() {
  return {
    products: [
      {
        id: 1,
        name: "Beef Bobotie with Yellow rice",
        price: 122,
        img: 'https://i.postimg.cc/5NYmsvR7/x-Beef-Bobotie-Yellow-Rice-768x768-jpg-pagespeed-ic-iewnw-Q-sk-R-1.webp'
      },
      {
        id: 2,
        name: "Spaghetti Bolongnese",
        price: 175,
        img: ("https://i.postimg.cc/pX1f9Cks/x-Spaghetti-Bolongnese-768x768-jpg-pagespeed-ic-ip-QL-c-Icf-U.webp")
      },
      {
        id: 3,
        name: "Italian Mince Meatballs  ",
        price: 65,
        img: ("https://i.postimg.cc/tTKdgNbs/x-Meatballs-Ratatouille-Pasta-550x550-jpg-pagespeed-ic-o9-Ca-Ezb186.jpg")
      },
{
  id: 4,
        name: "Rosemary Chicken &Rice",
        price: 123,
        img: ("https://i.postimg.cc/NG1s4Kk6/x-Rosmary-Chicken-Peas-Carrots-Rice-550x550-jpg-pagespeed-ic-zsnp6-A0-B11.webp")
}
    ]
  }
   },
   components: { },

 

}

</script>


<style>
#app {
  
  text-align: center;
  color: #0d0d0d;
  margin-top: 60px;
}
body{
  background-color:rgb(119, 153, 152);
}
.image{
  width:210px
}

#data-search{
margin-right: -90%;

}

.expensive {
  font-weight: bolder;
  color: green;
}
.cheap {
  color: red;
}


.dropdown{
  text-align: left;
}
</style>
 
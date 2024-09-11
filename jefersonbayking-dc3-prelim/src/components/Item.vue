<script>
export default {
    
    name: 'Item',
    props: ['product'],
    methods: {
        addToCart(product){
            console.log(product)
        }
    }
}
</script>

<template>
  <div class="item">
    <h3>{{ product.name }}</h3>
    <p>Price: ₱{{ product.price }}</p>
    <button @click="addToCart(product)">Add to Cart</button>
  </div>
</template>

<style scoped>
.item{
  background-color: rgb(255, 255, 255);
  margin: 10px 10px;
  border-radius: 10px;
  transition: ease-in-out .3s;
  width: 25%;
}


.item:hover{
  transform: translateY(5px);

}


button{
  background-color: #f1f1f1;
  border: none;
  padding: 10px 15px;
  border-radius: 10px;
  transition: ease-in-out .3s;
  margin: 10px auto;

}

button:hover{
  scale: 104%;
  background-color: rgb(63, 226, 63);
}
</style>
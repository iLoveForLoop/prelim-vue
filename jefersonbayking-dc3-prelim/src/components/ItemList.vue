<script>
import Item from './Item.vue'
export default {

    name: 'ItemList',
    props: ['products'],
    components: {Item},
    data(){
        return{
            
        }
    },
    methods: {
      
    }
}

</script>

<template>
  <div class="item-list">
        <h2>Product List</h2>
        <div class="list-container">
          <Item v-for="product in products" :key="product.id" :product="product" />
        </div>
        
  </div>
</template>



<style scoped>

.item-list{
  padding: 20px;
  margin: 30px auto;
  text-align: center;
  align-content: center;
  background-color: #e9e9e9;
  box-shadow: 5px 5px 5px 5px grey;
  max-width: 550px;
}

.list-container{
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}

</style>
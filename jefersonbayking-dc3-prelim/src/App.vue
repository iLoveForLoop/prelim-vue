<script>
import ItemList from './components/ItemList.vue';

export default{
    name: 'App',
    components: { ItemList},
    data(){
        return{
            isShowing: false,
            searchedItem: '',
            searchedProducts: [],
            products: [
                {id: 1, name: 'Product 1', price: 20},
                {id: 2, name: 'Product 2', price: 300},
                {id: 3, name: 'Test 2', price: 300},
                {id: 4, name: 'Product 2', price: 200},
                {id: 5, name: 'Product 2', price: 999},
                {id: 6, name: 'Product 2', price: 310},
                {id: 7, name: 'Product 2', price: 310},
                {id: 8, name: 'Jeferson', price: 310},
                {id: 9, name: 'Bayking 3', price: 50}
            ]
            
        }
    },
    computed: {
        searchData(){
            return this.products.filter(product => this.searchedItem ? product.name.toLowerCase().includes(this.searchedItem.toLowerCase()) : false)
        }
    },
    methods: {
        update(){
            if(this.searchedItem == ''){
                this.searchedProducts = null
            }else{
                this.searchedProducts = this.products.filter(product => product.name.toLowerCase().includes(this.searchedItem.toLowerCase()))
            }
             
        },
        toggle(){
          this.isShowing = !this.isShowing
        }
    }
    
}
</script>

<template>
  <div class="top">
    <input type="text" v-model="searchedItem" placeholder="Search for an item">
    <button type="button" @click="update">Search</button>
  </div>
    

    <div v-if="isShowing">
      <ItemList :products="searchedProducts"/>
    </div>
    
    <div class="btn-div">
      <button @click="toggle">{{ isShowing ? 'Hide' : 'Show' }}</button>
    </div>
    
</template>

<style scoped>
.top{
  text-align: center;
}

.btn-div{
  margin-top: 50px;
  text-align: center;
}

button{
  padding: 10px 25px;
  color: rgb(0, 0, 0);
  border: none;
  margin: auto;
  transition: .3s ease-in-out;
}

button:hover{
  background-color: rgb(33, 179, 76);
}

</style>
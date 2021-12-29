<template>



 <nav>
   <h1>Mellan-dags REA</h1>
 <ul>

<li v-for="item in CartItems" :key=item.itemPrice>

<p>{{item.itemTitle}}</p>
<img width="100" :src= item.itemImg />
<p>{{item.itemPrice}} SEK</p>


</li>

   </ul>


 </nav>
  <section class="Items-style">

    <div>
      
 <SaleItem @click=ToggleItem(1)  msg="Fien shoes" App img="https://images.unsplash.com/photo-1515955656352-a1fa3ffcd111?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxzZWFyY2h8MTN8fHdpbnRlciUyMHByb2R1Y3R8ZW58MHx8MHx8"
 
 price=1000
 
 
 />
  
      </div>

  
    <SaleItem @click=ToggleItem(2) msg="Snowglazes" img= "https://images.unsplash.com/photo-1614358536373-1ce27819009e?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1169&q=80"/>
  <SaleItem @click=ToggleItem(3) msg="Dronerer" img="https://images.unsplash.com/photo-1523132797263-747d5d0dbbb3?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=774&q=80"/>
 
 <aside >
  

   
 </aside>
 
  </section>

<section  class="Items-center" >
    



    <div class="buy-box">  <img class="add-to-basket" @click=AddToCart()  src="https://www.clipartmax.com/png/full/219-2194400_basket-basket-icon.png"/>
    <SaleItem  :msg=ViewingItems.itemTitle :img=ViewingItems.itemImg  :price="ViewingItems.Price"/>
</div>


  <span>
<button @click=ToggleItem(1)>See Item 1</button>
<button @click=ToggleItem(2)>See Item 2</button>
<button @click=ToggleItem(3)>See Item 3</button>
  </span>


</section>

</template>

<script>
import SaleItem from './components/SaleItem.vue'

export default {
  name: 'App',
  components: {
    SaleItem
  },

data(){
return{
ViewingItems:[],
SavedItems:[],
// itemTitle:'test',
// itemImg:'',
// itemPrice:0,

CartItems:[],

ItemNr:0


}

},


  methods:{

    ToggleItem(f){

      if (f==1){

   this.ViewingItems.itemTitle="shoes",
         this.ViewingItems.itemImg="https://images.unsplash.com/photo-1515955656352-a1fa3ffcd111?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxzZWFyY2h8MTN8fHdpbnRlciUyMHByb2R1Y3R8ZW58MHx8MHx8"
        

      this.SavedItems.push({
        
        
        
        itemTitle:"shoes",
        itemImg:"https://images.unsplash.com/photo-1515955656352-a1fa3ffcd111?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxzZWFyY2h8MTN8fHdpbnRlciUyMHByb2R1Y3R8ZW58MHx8MHx8",
        itemPrice:1000
        
        
        })
 

        }
     if (f==2){
      this.ViewingItems.itemTitle="Snowglazers"
      this.ViewingItems.itemImg="https://images.unsplash.com/photo-1614358536373-1ce27819009e?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1169&q=80"



      this.SavedItems.push({
        
        
        
        itemTitle:"Snowglazers",
        itemImg:"https://images.unsplash.com/photo-1614358536373-1ce27819009e?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1169&q=80",
        itemPrice:500
        
        
        })


        }
    
    if (f==3){
      this.ViewingItems.itemTitle="Drorne"
      this.ViewingItems.itemImg="https://images.unsplash.com/photo-1523132797263-747d5d0dbbb3?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=774&q=80"
        
        
      this.SavedItems.push({
        
        
        
        itemTitle:"Drorne",
        itemImg:"https://images.unsplash.com/photo-1523132797263-747d5d0dbbb3?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=774&q=80",
        itemPrice:23000
        
        
        })
        
        
        
        
        }

        
    
      
    },
    AddToCart(){

       this.CartItems.push(this.SavedItems.pop())
      
      
      // (element => {
      //   this.CartItems.push(element)
      //   console.log(element)
      // });
      
    }
  }
}
</script>

<style>
nav ul{

  display: flex;
  background-color: rgba(255, 255, 255, 0.5);
}


nav ul li{
  display: flex;
flex-direction: column;
padding: 1rem;
background-color: rgba(255, 250, 200, 0.2);
border-radius: 10px;
border: 1px solid wheat;


}


nav ul li p{

  color: darkolivegreen;

}

h1{
  font-size: 3rem;
  background-color: rgba(255, 255, 255, 0.7);
padding: 1rem;
}
#app {
  background-image: url(https://images.unsplash.com/photo-1512730129227-9cfa8f234591?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1924&q=80);
  background-size: contain;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  
}


.Items-style{
display:grid;
grid-template-columns: 1fr 1fr 1fr;
padding: 1rem;
justify-content: center;

background-color: rgba(255, 255, 255, 0.7);
}

.Items-center{
display:flex;
flex-direction: column;
align-items: center;
justify-content: center;
background-color: rgba(225, 225, 225, 0.7);
padding: 5rem;


}

.buy-box{
display:flex;
}

.add-to-basket{
max-width: 2rem;
max-height: 2rem;
}


button{
  background-color: azure;
  padding: 1rem;
  margin: 1rem;
}

</style>

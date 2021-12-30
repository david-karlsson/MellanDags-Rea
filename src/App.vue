<template>



 <nav>
   <h1>Mellan-dags REA</h1>

<hr/>
    <!-- ~ Cart -->
 <ul>


<img class="add-to-basket"  src="https://www.clipartmax.com/png/full/219-2194400_basket-basket-icon.png"/>
<li v-for="item in CartItems" :key=item.itemPrice>
<p>{{item.itemTitle}}</p>
<img width="100" :src= item.itemImg />
<p>{{item.itemPrice}} SEK</p>


</li>

   </ul>
<!-- End -Cart -->

 </nav>
  <section class="Items-style">


<!-- 
<ul :v-for="item in AllItems" :key=item.id>


<SaleItem @click=ToggleItem(1)  msg=item.ItemTitle  img="https://images.unsplash.com/photo-1515955656352-a1fa3ffcd111?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxzZWFyY2h8MTN8fHdpbnRlciUyMHByb2R1Y3R8ZW58MHx8MHx8"
 
 price=1000
 
 
 />

</ul> -->


    <div>

      
      
 <SaleItem @click=ToggleItem(1)  msg="Fien shoes" App img="https://images.unsplash.com/photo-1515955656352-a1fa3ffcd111?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxzZWFyY2h8MTN8fHdpbnRlciUyMHByb2R1Y3R8ZW58MHx8MHx8"
 
 price = 1000
 
 
 />
  
      </div>

  
    <SaleItem @click=ToggleItem(2) msg="Snowglazes" img= "https://images.unsplash.com/photo-1614358536373-1ce27819009e?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1169&q=80" price =  500 />
  <SaleItem @click=ToggleItem(3) msg="Dronerer" img="https://images.unsplash.com/photo-1523132797263-747d5d0dbbb3?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=774&q=80" price= 2300 />
 
 <aside >
  

   
 </aside>
 
  </section>

<section  class="Items-center" >
    



    <div class="buy-box" >  
     
    <SaleItem  :msg=SingleViewItem.itemTitle :img=SingleViewItem.itemImg :price="SingleViewItem.ItemPrice"/>
     <p class="buy-text" @click=AddToCart() >  <img class="add-to-basket"  src="https://www.clipartmax.com/png/full/219-2194400_basket-basket-icon.png"/>Lägg till i kundkorg</p>
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

AllItems:[
{
        
        
        id:1,
        itemTitle:"Sporty Shoes",
        itemImg:"https://images.unsplash.com/photo-1515955656352-a1fa3ffcd111?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxzZWFyY2h8MTN8fHdpbnRlciUyMHByb2R1Y3R8ZW58MHx8MHx8",
        itemPrice:1000
        
        
        },
        {
        
        
        id:1,
        itemTitle:"Snowglazers",
        itemImg:"https://images.unsplash.com/photo-1614358536373-1ce27819009e?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1169&q=80",
        itemPrice:500
        
        
        },
{
        
        
        id:3,
        itemTitle:"Drone",
        itemImg:"https://images.unsplash.com/photo-1523132797263-747d5d0dbbb3?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=774&q=80",
        itemPrice:23000
        
        
        }




],


SingleViewItem:{},
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

   this.SingleViewItem.itemTitle="shoes",
         this.SingleViewItem.itemImg="https://images.unsplash.com/photo-1515955656352-a1fa3ffcd111?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxzZWFyY2h8MTN8fHdpbnRlciUyMHByb2R1Y3R8ZW58MHx8MHx8",
        this.SingleViewItem.itemPrice = 1000

      this.SavedItems.push({
        
        
        
        itemTitle:"shoes",
        itemImg:"https://images.unsplash.com/photo-1515955656352-a1fa3ffcd111?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxzZWFyY2h8MTN8fHdpbnRlciUyMHByb2R1Y3R8ZW58MHx8MHx8",
        itemPrice:1000
        
        
        })
 

        }
     if (f==2){
      this.SingleViewItem.itemTitle="Snowglazers"
      this.SingleViewItem.itemImg="https://images.unsplash.com/photo-1614358536373-1ce27819009e?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1169&q=80"



      this.SavedItems.push({
        
        
        
        itemTitle:"Snowglazers",
        itemImg:"https://images.unsplash.com/photo-1614358536373-1ce27819009e?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1169&q=80",
        itemPrice:500
        
        
        })


        }
    
    if (f==3){
      this.SingleViewItem.itemTitle="Drorne"
      this.SingleViewItem.itemImg="https://images.unsplash.com/photo-1523132797263-747d5d0dbbb3?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=774&q=80"
        
        
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

nav{
  background-color: rgba(255, 255, 255, 0.5);
display: grid;
grid-template-columns: 1fr 1fr 1fr;
border: 1px solid grey;


}
nav ul{

  display: flex;
  border: 1px solid grey;

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


h3{
  padding:1rem;
    background-color: rgba(187, 83, 83, 0.2);

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

.buy-text{

padding: 1rem;
  color: darkslategrey;
  border: 1px dashed salmon;
  max-height:5vh;
}

.add-to-basket{
max-width: 2rem;
max-height: 2rem;
padding-right: 1rem;
}

.buy-text:hover{
  cursor: pointer;
  border: 1px solid salmon;
}





button{
  background-color: azure;
  padding: 1rem;
  margin: 1rem;
}

</style>

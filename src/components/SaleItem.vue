<template>
  <div class="item">
    <h2>{{ msg }}</h2>
    <p>
     <img :src=img />
<strong>{{price}} SEK</strong>


    </p>
  
  </div>
</template>

<script>
export default {
  name: 'SaleItem',
  props: {
    msg: String,
    img:String,
    price:Number
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->



<style scoped>


.item{
  display: flex;
  flex-direction: column;
 justify-content: center;
 max-width: 20vw;
 padding:1rem

  }

.item:hover{

cursor: pointer;}

img{
max-width: 30vw;
max-height: 20vw;
padding: 1rem;

}

h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {

  padding: 1rem
}
a {
  color: #42b983;
}
</style>

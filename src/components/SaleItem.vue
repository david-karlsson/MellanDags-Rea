<template>
  <div class="item">
    <h2>{{ msg }}</h2>
    <p>
     <img :src=img />


    </p>
  

<strong>{{cat}}</strong>
<em>
{{desc}}
</em>
<strong>{{price}} SEK</strong>

  </div>
</template>

<script>
export default {
  name: 'SaleItem',
  props: {
    msg: String,
    img:String,
    price:Number,
    desc:String,
    cat:String
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

a {
  color: #42b983;
}

p, strong{
  margin: 1rem;
}

strong{
  color: darkgreen;
  text-transform: uppercase;
}

em{
letter-spacing: 1px;
line-height: 1.7;
background: azure;
padding: 2rem;
color: darkslategrey;

}

em::first-letter{
  color: darkred;
  text-transform: uppercase;
  font-weight: bold;
  font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
}
</style>

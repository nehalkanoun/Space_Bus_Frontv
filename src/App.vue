<template>
  <div class="navbar">
<img src="\src\assets\download-removebg-preview.png">
<span class="text">Space Bus</span></div>

<div class="image-container">
  <img src="/src/assets/map.png">
    </div>

<button @click="next()" class="button21 text1">Book Ticket</button>


<table class="table">
  <thead>
    <tr>
      <th>Bus_ID</th>
      <th>From</th>
      <th>Departure</th>
      <th>To</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>B294</td>
      <td>Hawari</td>
      <td>7:35 pm</td>
      <td>baloun</td>
    </tr>
    <tr>
      <td>B222</td>
      <td>baloun</td>
      <td>8:35 pm</td>
      <td>hawari</td>
    </tr>
    <tr>
      <td>B292</td>
      <td>qarunis</td>
      <td>7:00 pm</td>
      <td>hadaiq</td>
    </tr>
    <tr>
      <td>B789</td>
      <td>hadaiq</td>
      <td>6:35 pm</td>
      <td>sidi hussian</td>
    </tr>
    <tr>
      <td>B123</td>
      <td>sidi hussian</td>
      <td>5:35 pm</td>
      <td>hawari</td>
    </tr>
  </tbody>
</table>

<div v-if="open_page">
<BookTicket @delete="openVCC()" @exit="next()" />
</div>
<div v-if="openvc">
<vccode @cancel="cancelvc()" @openT="openTT()"/>
</div>

<div v-if="open_T">
  <Ticket @delete="cancelT()"/>
</div>

</template>










<script>
import BookTicket from './components/BookTicket.vue'
import vccode from './components/vccode.vue'
import Ticket from './components/Ticket.vue'
export default{
  data() {
    return {
    open_page:false,
    openvc:false,
    open_T:false
    }
  },
  name: "App",
  components: { BookTicket, vccode, Ticket},
methods:{
  next(){
    this.open_page=!this.open_page

  },
  cancelvc(){
    this.openvc=!this.openvc
  },

  cancelT(){
    this.open_T=!this.open_T
  },
  openVCC(){
    this.open_page=!this.open_page
    this.openvc=!this.openvc
  },
  openTT(){
    this.open_T=!this.open_T
    this.openvc=!this.openvc
  }
}
}
</script>







<style >
.button21{

  display: flex;
  justify-content: center;
 margin-left:45%;
 margin-right:55%;
 margin-top:30px;
  width: 150px;
height: 50px;
flex-shrink: 0;
border-radius: 7px;
background: #197639;
padding-top:12px ;
border-color: white;
scroll-snap-stop:always ;
cursor: pointer;
}

.navbar {
  display: flex;
  align-items: center;
  background: #197639;
  padding: 3px;
}

.navbar img {
  height: 80px;
  margin-right: 10px;
}

.text {
  font-size: 20px;
 
  font-family: sans-serif;
  color:white;
}
.text1{
  font-size: 20px;
 
  font-family: sans-serif;
  color:white;

}
.image-container {
  display: flex;
  justify-content: center;
  margin-top: 30px;
  margin-left:30px;
  margin-right: 30px;
}

.image-container img {
  max-width: 60%;
  height: auto;

}
/* Responsive styles */
@media screen and (max-width: 600px) {
  .navbar {
    flex-direction: column;
    justify-content: center;
    text-align: center;
  }

  .navbar img {
    margin-bottom: 3px;
  }
}
body{
  margin:0;
}









.table {
  border-collapse: collapse;
  width: 50%;
  margin-left:23%;
  margin-top:30px;
  margin-bottom:30px ;
}

.table th,
.table td {
  border: 1px solid #ddd;
  padding: 8px;
  text-align: center;
  font-family: sans-serif;
  margin-left:25%

}

.table th {
  
  font-weight: bold;
  background: #82ba96;
  color:rgb(44, 43, 43);
}

.table tr:nth-child(even) {
  background-color: #f9f9f9;
}



.table td:last-child {
  text-align: center;
  font-family: sans-serif;
  
}
</style>

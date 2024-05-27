<template>
    <div class="background">
    <div class="navbar">
        <img src="\src\assets\download-removebg-preview.png">
        <span class="text">Space Bus</span>
    </div>
    <div class ="image-container">
    <img src="\src\assets\QRcode.png" class="">
    <img src="\src\assets\exit.png" class="exit" @click="nextpg()">
</div>
<div class="ticketno">
<h1>BT234-5</h1>
</div>

<div class="grayc">

    <div class="text2">
        <p>Bus_ID: B294</p>
    </div>
    <div class="whiteborder">
        <span class="lefttopside">From</span>
        <span class="righttopside">To</span>
        <div class="imgA">
        <img src="\src\assets\arrow.png">
    </div>
            <span class="leftbottomside">بوهديمه</span>
        <span class="rightbottomside">هواري</span>
    </div>
    <div class="text2">
        <p>Number of passengers: {{ Numpassengers }}</p>
        <p>Date: {{ Date }}</p>
        <p>Departure Time: {{ Departure }}</p>
        <p>Price: {{ Price }} Dinar</p>
    </div>

  </div>








</div>
</template>



<script >
export default {
  data(){
    return{
        Numpassengers:'',
        Date:'',
        Departure:'',
        Price:''
    }
},
methods:{
  nextpg(){
  this.$emit("delete")
 
}
}
}
</script>



<style scoped>
.exit{
width:35px;
height:35px;
right:10px;
display:flex;
cursor: pointer;
position:absolute;
}
.text {
  font-size: 20px;
  font-family: sans-serif;
  color:white;
}
.text2{
    color:black; 
    font-size: 20px;
    font-family: sans-serif;
    margin-left: 30px;
    font-weight: bold;
   
}
.grayc{
    background-color: #D9D9D9;
    width: 100%;
    height: 70%;
    border-radius: 33px 33px 0px 0px;
    padding-top: 20px;
    margin-top: 30px;
}
.whiteborder{
    position: relative;
    background-color: white;
    height: 200px;
    margin-left: 30%;
    margin-right:30%;
    min-width: 300px;
}

.imgA{
    display: flex;
    margin: auto 40% ;
    margin-top:70px;
    position: absolute;
}

.lefttopside{
position: absolute;
left:40px;
top:30px;
font-size: 25px;
font-family: sans-serif;
}
.righttopside{
    position: absolute;
    right:40px;
    top:30px;
    font-size: 25px;
    font-family: sans-serif;
}

.leftbottomside{position: absolute;
  left: 40px;
  bottom:30px;
  font-size: 25px;
  font-family: sans-serif;
}
.rightbottomside{
  position: absolute;
  right: 40px;
  bottom:30px;
  font-size: 25px;
  font-family: sans-serif;
}

.navbar {
  display: flex;
  align-items: center;
  background: #197639;
  padding: 3px;
}

.background{
    background: rgb(255, 253, 253);
    width: 100%;
    height:905px;
    position: absolute;
    top: 0;
    left: 0;
  
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

.navbar img {
  height: 80px;
  margin-right: 10px;
}
.ticketno{
text-align: center;
font-family: sans-serif;
font-size: 15px;
font-style: normal;
font-weight: 200;
line-height: normal;
}
</style>
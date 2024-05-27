<template>
<div class="background" @click.self="nextpg">
<form class="boxes" >
  <img src="\src\assets\exit.png" class="exit" @click="nextpg">
  <h1 class="title">Book Ticket</h1>

    <input type="string" class="textbox" placeholder="Verification Number" required v-model="VerificationNumber">


    <div class="info">
    <p>Bus ID: {{ bus_id }}</p>
    <p>Time: {{ Time }}</p>
    <p>Price: {{ Price }}</p>
</div>
<button @click="next" class="button1 text1">Pay</button>
</form>
</div>

</template>

<script>

export default {
data(){
    return{
VerificationNumber:'',
        bus_id:'',
        Time:'',
        Price:'',
        
    }
},
methods:{
next(){
  this.$emit("openT")
},
nextpg(){
  this.$emit("cancel")
},
}
}
</script>

<style scoped>
.exit{
  width: 20px;
height: 20px;
flex-shrink: 0;
flex-direction:row;
display:flex;
margin-left: 100%;
cursor: pointer;
}
.title{
  color: #000;
font-family: sans-serif;
font-size: 20px;
font-weight: bold;
line-height: 18px; /* 90% */
letter-spacing: 0.6px;
flex-direction:row;
display:flex;
}

.info{
  margin-right:45%;
  font-family: sans-serif;
  margin-top: 30px;
}

.background{
    background: rgba(25, 25, 25, 0.70);
    width: 100%;
    height:905px;;
position: absolute;
  top: 0;
  left: 0;
 
}

.boxes{
    min-width:300px;
    max-width: 35%;
    min-height: 640px;
    margin: 30px auto;
    background: #D9D9D9;
    text-align: left;
    padding: 40px;
    border-radius: 33px;
    align-items: center;
    display: flex;
    flex-direction: column;

}



.textbox{
display: block;
width: 60%;
padding: 11px 18px;
justify-content: space-between;
align-items: center;
border-radius: 8px;
box-sizing: border-box;
border: 1.3px solid var(--Blues-Gray2, #b8bbc2);
background: var(--White, #FFF);
margin-top:30px;
cursor: pointer;
}


.button1{
display: flex;
justify-content: center;
width: 150px;
height: 50px;
flex-shrink: 0;
border-radius: 7px;
background: #197639;
padding-top:12px ;
border-color: white;
margin-top:30px;
cursor: pointer;
}
.text1{
  font-size: 20px;
  font-family: sans-serif;
  color:white;
}

</style>















<template>
    <h1 @click.self="closemodal2">hello </h1>
</template>

<script>

export default {
methods:{
closemodal2(){
    this.$emit("delete")
}

}
}
</script>


<template>
    <div class="backdrop" @click.self="closemodal">
        <div class ="modal">

<slot>default content</slot>
<slot name="links"></slot>
        </div>
    </div>
</template>
<style scoped>

.backdrop {
width: 390px;
height: 844px;
flex-shrink: 0;
background: rgba(85, 53, 53, 0.7);
}
</style>

<script>

export default {
props:[],
methods:{
    closemodal(){
        this.$emit("close")
    }
}
}

</script>

<template>
    <div class="hello">
        <button v-on:click="hello">hello</button>
    </div>
</template>
  
<script>
export default {
    name: 'NavBar',
    props: {
        msg: String,
    },
    data(){
    },
    methods: {
        hello(){
            alert(this.name)
        }

    }
}
</script>
  
  <!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
div {
    background-color: red;
    padding: 10px;
}
</style>


  
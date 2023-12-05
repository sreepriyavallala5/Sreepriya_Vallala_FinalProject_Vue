<template>
    <div>
    <header>
            <h1>{{Name1}}<span>{{Name2}}</span></h1>    
    </header>      
    </div>
</template>
    
<script> 
    export default{
        name: 'Header',
        props:{
            Name1: String,
            Name2: String,
            paragraph: String
        }
    }
</script>

<style scoped>
    div{
        text-align: center;
        color: white;
        font-family: 'Times New Roman', Times, serif;
        }
    h1{
    color: #ADEFD1FF;
    font-size: 28px;
    }
    span{
      color: #FBF7F4;
    }
    header{
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 20px 16px;
    background-color: #00203FFF;
    box-shadow: 0px 0px 6px rgba(0, 0, 0, 0.1);
    } 
</style>
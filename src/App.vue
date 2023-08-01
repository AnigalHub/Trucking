<template>
  <div id="app">
      <Navbar/>
      <Home/>
      <Advantages/>
      <Types/>
      <About/>
  </div>
</template>
<script>
    import Home from "@/components/Home";
    import Navbar from "@/components/Navbar";
    import Advantages from "@/components/Advantages";
    import Types from "@/components/Types";
    import About from "@/components/About";
    export default {
        name: 'App',
        components: {
            About,
            Types,
            Advantages,
            Navbar,
            Home,
        },
    }
</script>

<style lang="scss">

    body{
        background: #010101;
    }
    /*вся страница*/
    #app{
        height: 100%;
        margin: 0 !important;
        padding: 0 !important;
        background: #010101;
        color: white;
    }
    /*контейнер на блоки посередине экрана*/
    .container{
        padding-right: 15px !important;
        padding-left: 15px !important;
    }
    #Types{
        min-height: 75vh;
    }
    #Advantages{
        background: url("../public/bgAd2.png") no-repeat;
        background-size: cover;
        padding: 15px 0 50px;
    }
    /*заголовки*/
    h1{
        margin-top: 8% !important;
        margin-bottom: 10% !important;
        color: white;
        font-size: 3.7rem !important;
        line-height: 3.8rem;
    }
    p{
        font-family: "Montserrat", sans-serif;
        font-size: 1.25rem;
        font-weight: 400 !important;
        margin-bottom: .5rem !important;
    }
    #Home button{
        color: white;
        background: transparent;
        text-align: center;
        display: block;
        padding: 8px 85px !important;
        border-radius: 10px;
        font-size: 1.2rem;
        border: 2px solid #FF7A00;
        z-index: 10;
        position: relative;
        /*при наведении*/

    }
    #Home{
        padding: 40px 0 100px;
        p{
            font-size: 1.45rem;
            margin-bottom: 8% !important;
        }
        .carousel {
            margin-top: 10%;
            width: 95%;
            margin-left: -2%;
        }
        .shadow{
            position: absolute;
            border: 5px solid #FF7A00;
            top: 5%;
            left: 9%;
            height: 102%;
            width: 88%;
        }
    }
    h2{
        padding-top: 30px;
        padding-bottom: 30px;
        font-weight: 400 !important;
        letter-spacing: 1.5px;
        font-size: 1.7rem !important;
        color: white;
        text-transform: uppercase;
        text-align: center;
    }
    h3{
        color: #FF7A00;
        text-align: center;
        padding-bottom: 15px;
    }
    #Advantages{
        .title {
            overflow: hidden;
            text-align: center;
        }
        .title span {
            display: inline-block;
            vertical-align: middle;
        }
        .title:before,
        .title:after {
            content: "";
            display: inline-block;
            vertical-align: middle;
            width: 20%;
            height: 2px;
            background-color: #FF7A00;
            position: relative;
        }
        .title:before {
            margin-left: -100%;
            left: -25%;
        }
        .title:after {
            margin-right: -100%;
            right: -25%;
        }
    }
    #Types{
        padding: 15px 0 50px;
        h2{
            text-decoration: underline;
            text-underline-offset: 10px;
            text-decoration-color: #FF7A00;
        }
    }
</style>

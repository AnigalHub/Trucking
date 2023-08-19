<template>
  <div id="app">
      <Navbar/>
      <Home/>
      <Advantages/>
      <Types/>
      <About/>
      <Stages/>
      <Customs/>
      <Calculation/>
      <Package/>
      <MyFooter/>
  </div>
</template>
<script>
    import Home from "@/components/Home";
    import Navbar from "@/components/Navbar";
    import Advantages from "@/components/Advantages";
    import Types from "@/components/Types";
    import About from "@/components/About";
    import Stages from "@/components/Stages";
    import Customs from "@/components/Customs";
    import Calculation from "@/components/Calculation";
    import Package from "@/components/Package";
    import MyFooter from "@/components/MyFooter";
    export default {
        name: 'App',
        components: {
            MyFooter,
            Package,
            Calculation,
            Customs,
            Stages,
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
    /*контейнер, который включает в себя повтор блоков*/
    .flex-container{
        display: flex;
        flex-wrap: wrap;
    }
    #Advantages{
        background: url("../public/bgAd2.png") no-repeat;
        background-size: 100% 100%;
        padding: 15px 0 50px;
    }
    #Customs{
        background: url("../public/bgCustoms2.png") no-repeat;
        background-size: 100% 100%;
        padding: 15px 0 50px;
    }
    #Package{
        background: url("../public/bgPack2.jpg") no-repeat;
        background-size: 100% 100%;
        padding: 15px 0 50px;
    }
    img{
        width: 100%;
    }
    /*заголовки*/
    h1{
        margin-top: 8% !important;
        margin-bottom: 10% !important;
        color: white;
        font-size: 3.7rem !important;
        line-height: 3.8rem;
    }
    p,.form-control, .btn{
        font-family: "Montserrat", sans-serif;
        font-size: 1.25rem;
        font-weight: 400 !important;
        margin-bottom: .5rem !important;
    }
    .btn{
        font-size: 1.35rem !important;
    }
    .form-control{
        font-size: 1.1rem !important;
    }
    input::placeholder{
        color: white !important;
    }
    .switch {
        position: relative;
        display: inline-block;
        width: 60px;
        height: 34px;
    }
    .switch input {
        opacity: 0;
        width: 0;
        height: 0;
    }
    .slider {
        position: absolute;
        cursor: pointer;
        top: 0;
        left: 0;
        right: 0;
        bottom: 0;
        background-color: #ccc;
        -webkit-transition: .4s;
        transition: .4s;
    }
    .slider:before {
        position: absolute;
        content: "";
        height: 26px;
        width: 26px;
        left: 4px;
        bottom: 4px;
        background-color: white;
        -webkit-transition: .4s;
        transition: .4s;
    }
    /* Rounded sliders */
    .slider.round {
        border-radius: 34px;
    }
    .slider.round:before {
        border-radius: 50%;
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
    #Advantages, #Customs, #Package{
        h2 {
            overflow: hidden;
            text-align: center;
        }
        h2 span {
            display: inline-block;
            vertical-align: middle;
        }
        h2:before, h2:after{
            content: "";
            display: inline-block;
            vertical-align: middle;
            width: 20%;
            height: 2px;
            background-color: #FF7A00;
            position: relative;
        }

    }
    #Advantages, #Package{
        h2:before {
            margin-left: -100%;
            left: -25%;
        }
        h2:after {
            margin-right: -100%;
            right: -25%;
        }
    }
    #Customs{
        h2:before {
            margin-left: -100%;
            left: -5%;
        }
        h2:after {
            margin-right: -100%;
            right: -5%;
        }
    }
    #Types, #Stages{
        padding: 15px 0 70px;
        h2{
            text-decoration: underline;
            text-underline-offset: 10px;
            text-decoration-color: #FF7A00;
        }
    }
    #About{
        background: url("../public/bgAbout2.png") no-repeat;
        background-size: 100% 100%;


    }
    #About, #Calculation{
        padding: 15px 0 80px;
        h2{
            color: #FF7A00;
            padding-top: 5%;
            font-size: 2.5rem !important;
        }
    }
    #MyFooter{
        padding: 40px;
    }
</style>

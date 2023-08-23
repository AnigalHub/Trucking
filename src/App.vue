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
<style>
    #About .carousel-indicators{
        display: none !important;
    }
</style>
<style lang="scss">
    @mixin h2Underline{
        text-decoration: underline;
        text-underline-offset: 10px;
        text-decoration-color: #FF7A00;
    }
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
    #Advantages, #Customs, #Package{
        h2 {
            overflow: hidden;
            text-align: center;
            span {
                display: inline-block;
                vertical-align: middle;
            }
            &:before, &:after {
                content: "";
                display: inline-block;
                vertical-align: middle;
                width: 20%;
                height: 2px;
                background-color: #FF7A00;
                position: relative;
            }
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
    #Types h2, #Stages h2{
        /*миксин*/
        @include h2Underline;
    }
    #About, #Calculation{
        h2{
            color: #FF7A00;
            padding-top: 5%;
            font-size: 2.5rem !important;
        }
    }
    h3{
        color: #FF7A00;
        text-align: center;
        padding-bottom: 15px;
    }
    p, .form-control, .btn, li {
        font-family: "Montserrat", sans-serif;
        font-size: 1.2rem;
        font-weight: 400 !important;
        margin-bottom: .5rem !important;
    }
    a{
        color: white !important;
        text-decoration: none;
        &:hover{
            color: white;
        }
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
    #Advantages{
        background: url("../public/bgAd2.png") no-repeat;
    }
    #About{
        background: url("../public/bgAbout2.png") no-repeat;
    }
    #Customs{
        background: url("../public/bgCustoms2.png") no-repeat;
    }
    #Package{
        background: url("../public/bgPack2.jpg") no-repeat;
    }
    #Advantages, #About, #Customs, #Package{
        background-size: 100% 100%;
    }
    #Advantages, #Customs, #Package, #Types, #Stages, #About, #Calculation{
        padding: 15px 0 60px;
    }
    .switch {
        position: relative;
        display: inline-block;
        width: 60px;
        height: 24px;
        margin-top: 5px;
        input{
            opacity: 0;
            width: 0;
            height: 0;
        }
    }
    .slider {
        position: absolute;
        cursor: pointer;
        top: 0;
        left: 0;
        right: 0;
        bottom: 0;
        background-color: rgba(160, 160, 160, 0.83);
        border-radius: 15px;
        transition: .4s;
        &:before {
            position: absolute;
            content: "";
            height: 16px;
            width: 16px;
            left: 4px;
            top: 4px;
            border-radius: 8px;
            background-color: white;
            -webkit-transition: .4s;
            transition: .4s;
        }
        /* Rounded sliders */
        .round {
            border-radius: 34px;
            &:before {
                border-radius: 50%;
            }
        }
    }
    .card{
        padding: 0 3.25rem;
        background: transparent !important;
    }
    .card-header {
        padding: 0 !important;
    }
    .card-text li{
        border: none;
        margin-top: 4% !important;
    }
    #Stages, #Types{
        .nav-pills .nav-link {
            display: flex;
            color: white;
        }
        .nav-item{
            border: 2px solid rgba(255, 122, 0, 0.6);
            border-radius: 5px;
            .nav-link{
                background-size: 100% 100% !important;
            }
            &:nth-child(4){
                margin-bottom: 0 !important;
            }
        }
        .tab-content{
            margin-left: 10px;
            border: 2px solid rgba(255, 122, 0, 0.37);
        }
    }
    button{
        color: white;
        text-align: center;
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
            img{
                height: 400px;
            }
        }
        .shadow{
            position: absolute;
            border: 4.5px solid #FF7A00;
            top: 5%;
            left: 9%;
            height: 102%;
            width: 88%;
        }
        button{
            background: transparent;
            padding: 8px 85px !important;
            border-radius: 10px;
            font-size: 1.2rem;
            border: 2px solid #FF7A00;
            z-index: 10;
            position: relative;
        }
    }
    #Advantages{
        .number{
            color: #FF7A00;
            font-size: 3.8rem;
            text-align: center;
            transform: scale(1.2, 1.2);
        }
        .descr{
            color: #FF7A00;
            text-align: center;
            margin-top: -15%;
        }
        .text{
            display: flex;
            height: 105px;
            align-items: center;
        }
        .col-2{
            padding: 0 !important;
        }
        .col{
            padding: 0 25px !important;
        }
        svg{
            padding: 8px;
        }
    }
    #Types{
        .nav-pills .nav-link {
            min-height: 120px;
            justify-content: center;
            align-items: center;
        }
        .nav-pills .nav-link.active{
            color: #FF7A00 !important;
            filter: contrast(90%) brightness(150%);
        }
        .tab-content{
            background: url("../public/types/55.jpg");
            border-radius: 5px;
        }
        .nav-item{
            margin: 0 0 5px;
            &:nth-child(1) .nav-link{
                background: url("../public/types/11.jpg");
            }
            &:nth-child(2) .nav-link{
                background: url("../public/types/22.jpg");
            }
            &:nth-child(3) .nav-link{
                background: url("../public/types/33.jpg");
            }
            &:nth-child(4) .nav-link{
                background: url("../public/types/44.jpg");
            }
        }
    }
    #About{
        li{
            list-style-type:none;
            border-bottom: 2px solid rgba(255, 122, 0, 0.5);
            margin-bottom: 1.5rem !important;
        }
        p{
            text-align: center;
        }
        .number{
            color: #FF7A00;
            font-size: 6rem;
            text-align: center;
            transform: scale(1.2, 1.2);
        }
        .numbers{
            border-radius: 50%;
            width: 300px;
            height: 300px;
            padding: 20px 20px 0;
            margin: 28% auto 0 10%;
            border: 2px solid rgba(255, 122, 0, 0.5);
        }
    }
    #Stages{
        .nav-link{
            margin: -6% 6% 6% -8%;
        }
        .col-auto {
            width: 60% !important;
        }
        .flex-column {
            display: contents !important;
            li{
                width: 40%;
                float: left;
            }
        }
        .nav-pills .nav-link {
            align-items: end;
        }
        .nav-pills .nav-link.active{
            color: #8e4404 !important;
            filter: contrast(90%) brightness(190%);
            font-weight: 600 !important;
            border: 1px solid rgba(255, 122, 0, 0.37);
        }
        .tab-content{
            background: #1C1D1E;
            margin-top: 1%;
            height: 500px;
            border-radius: 10px;
        }
        .nav-item{
            min-width: 40%;
            margin: 4%;
            .nav-link{
                min-height: 220px !important;
            }
            &:nth-child(1) .nav-link{
                background: url("../public/stages/11.png");
            }
            &:nth-child(2) .nav-link{
                background: url("../public/stages/22.png");
            }
            &:nth-child(3) .nav-link{
                background: url("../public/stages/33.png");
            }
            &:nth-child(4) .nav-link{
                background: url("../public/stages/44.png");
            }
        }
        .card-text h4{
            text-align: center;
            font-weight: 700 !important;
            margin-top: -3%;
            margin-bottom: 5% !important;
        }
    }
    #Customs{
        img{
            filter: brightness(50%);
            margin-bottom: 6%;
        }
        svg{
            width: 60px;
            margin: 0 auto;
            display: block;
            position: absolute;
            top: 40%;
            left: 42%;
        }
    }
    #Calculation{
        .flex-container {
            width: 105%;
            margin-left: -2.5%;
            div{
                border: .25px solid rgba(255, 122, 0, 0.45);
                background: #1F1E1E;
                width: 20%;
                padding: 15px 0;
                &:first-child{
                    border-top-left-radius: 20px 20px;
                }
                &:nth-child(2),&:nth-child(7){
                    width: 23%;
                }
                &:nth-child(4),&:nth-child(9){
                    width: 17%;
                }
                &:nth-child(5){
                    border-top-right-radius: 20px 20px;
                }
                &:nth-child(6){
                    border-bottom-left-radius: 20px 20px;
                }
                &:last-child{
                    border-bottom-right-radius: 20px 20px;
                }
                p{
                    float: left;
                    font-size: 1.1rem;
                    margin-right: 10px;
                    padding: 0.375rem 15px;
                }
            }
        }
        button{
            margin-top: 30px;
            border-radius: 10px;
            width: 105%;
            margin-left: -2.5%;
            background: rgba(255, 122, 0, 0.2);
            padding: 15px 0;
            border: .25px solid rgba(255, 122, 0, 0.45);
        }
        .form-control {
            background: transparent;
            border: none;
        }
        svg{
            padding-left: 15px;
        }
    }
    #Package{
        .flex-container {
            .row{
                width: 49%;
                padding: 15px;
            }
            .name{
                @include h2Underline;
            }
        }
    }
    #MyFooter{
        padding: 40px;
        svg{
            width: 30px;
        }
    }
</style>

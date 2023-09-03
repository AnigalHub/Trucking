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
    /*картинка в модальном окне*/
    .modal-dialog img{
        width: 100% !important;
        box-shadow: none !important;
    }
    /*"крестик" (размер) - кнопка закрытия модального окна*/
    .close {
        font-size: 2rem !important;
        padding: 1rem .5rem !important;
        color: white !important;
    }
    /*заголовок модального окна*/
    .modal-header{
        padding: .5rem 1.5rem !important;
    }
    /*контент модального окна*/
    .modal-content{background: #2a2929 !important;}
    /*фразы в заголовке модального меню*/
    .modal-title{font-weight: 600;}
    /*тело модального окна*/
    .modal-body {padding: 0 1rem 1rem 1rem!important;}
    /*footer-модального окна*/
    .modal-footer {display: none !important;}
    @media (min-width: 992px){
        /*ширина модального окна на разных экранах*/
        .modal-lg, .modal-xl {max-width: 720px !important;}
    }
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
        font-size: 1.1rem;
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
        color: rgba(255, 255, 255, 0.5) !important;
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
    input:checked + .slider {
        background-color: rgba(255, 122, 0, 0.45);
    }
    input:checked + .slider:before {
        transform: translateX(36px);
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
                //margin-bottom: 0 !important;
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
            text-align: center;
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
        .col{
            padding-right: 4rem !important;
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
            border-radius: 5px;
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
        .carousel{
            display: none;
        }
        .flex-container{
            align-items: center;
            justify-content: center;
        }
        .flex-container div{
            width: 33%;
            padding: 0 15px;
            position: relative;
        }
        img{
            filter: brightness(50%);
            margin-bottom: 6%;
            &:hover{
                filter: brightness(55%);
                cursor: pointer;
            }
        }
    }
    #Calculation{
        .flex-container {
            width: 105%;
            margin-left: -2.5%;
            div{
                border: .25px solid rgba(255, 122, 0, 0.45);
                background: #1F1E1E;
                width: 17%;
                padding: 15px 0;
                &:first-child{
                    border-top-left-radius: 10px 10px;
                }
                &:nth-child(2),&:nth-child(1),&:nth-child(6),&:nth-child(7), &:nth-child(3),&:nth-child(8){
                    width: 21.5%;
                }
                &:nth-child(5){
                    border-top-right-radius: 10px 10px;
                }
                &:nth-child(6){
                    border-bottom-left-radius: 10px 10px;
                }
                &:last-child{
                    border-bottom-right-radius: 10px 10px;
                }
                p{
                    color: rgba(255, 255, 255, 0.5) !important;
                    float: left;
                    font-size: 1.1rem;
                    padding: 0.375rem 15px;
                }
            }
        }
        button{
            margin-top: 30px;
            border-radius: 10px;
            width: 103.5%;
            margin-left: -2.5%;
            background: rgba(255, 122, 0, 0.2);
            padding: 15px 0;
            border: .25px solid rgba(255, 122, 0, 0.45);
        }
        .form-control {
            color: white;
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
        padding: 40px 0 10px;
        .flex-container .inf{
            width: 50%;
            margin-bottom: 2%;
        }
        svg{
            width: 30px;
        }
    }

                /*АДАПТИВНОСТЬ*/
    @media screen and (min-width: 992px) and (max-width: 1200px){
        h1{
            font-size: 3.2rem !important;
            line-height: 3.5rem;
        }
        #About, #Calculation{
            h2{
                font-size: 2rem !important;
            }
        }
        .form-control, .btn, li{
            font-size: 1.15rem !important;
        }
        p{
            font-size: 1.15rem;
        }
        #Advantages, #Customs, #Package, #Types, #Stages, #About, #Calculation {
            padding: 15px 0 40px;
        }
        #Home{
            p,button, .btn {
                font-size: 1.25rem !important;
            }
           .carousel img {
                height: 350px;
           }
        }
        #Advantages{
            .number {
                font-size: 3.2rem;
            }
           svg {
                padding: 5px;
           }
        }
        #Types{
            h3{
                padding-bottom: 10px;
                font-size: 1.5rem;
            }
            .nav-pills .nav-link {
                height: 130px !important;
            }
            .card {
                padding: 0 2rem;
            }
        }
        #About{
            .numbers {
                width: 285px;
                height: 285px;
                margin: 28% auto 0 1%;
            }
        }
        #Stages{
            h3{
                font-size: 1.4rem;
                margin-bottom: 0.25rem;
            }
            h4{
                font-size: 1.2rem;
            }
            .nav-item .nav-link {
                min-height: 190px !important;
            }
           .tab-content {
                height: 430px;
           }
           .card-body{
               line-height: 1.55rem;
           }
        }
        .slider{
            width: 50px;
        }
        #Calculation{
            .flex-container, button {
                width: 100%;
                margin-left: 0;
            }
            .flex-container{
                div {
                    width: 19.5%;
                    padding: 10px 0;
                    &:nth-child(2),&:nth-child(1),&:nth-child(6),&:nth-child(7){
                        width: 19.5%;
                    }
                    p{
                        margin-right: 0;
                        padding: 0.3rem;
                        font-size: 1rem
                    }
                }

            }
            .form-control {
                padding: .3rem;
                font-size: 1rem !important;
            }
        }
        #Package{
            .col{
                padding-right: 0 !important;
            }
        }
        #MyFooter{
            .flex-container .inf{
                width: 40%;
                .row{
                    width: 100%;
                }
            }
        }
    }
    @media screen and (min-width: 768px) and (max-width: 992px){
        h1{
            font-size: 2.5rem !important;
            line-height: 2.9rem;
        }
        h2{
          font-size: 1.35rem !important;
        }
        #About, #Calculation{
            h2{
                font-size: 1.4rem !important;
            }
        }
        .form-control, .btn, li{
            font-size: 1rem !important;
        }
        p{
            font-size: 1rem;
        }
        #Advantages, #Customs, #Package, #Types, #Stages, #About, #Calculation {
            padding: 15px 0 45px;
        }
        #Home{
            padding: 30px 0 80px;
            p,button, .btn {
                font-size: 1rem !important;
            }
            .carousel img {
                height: 290px;
            }
            .shadow{
                height: 99%;
            }
        }
        #Advantages{
            .number {
                font-size: 2.35rem;
            }
            svg {
                padding: 0;
            }
            .text {
                height: 80px;
            }
        }
        #Types{
            .col-auto {
                width: 40% !important;
            }
            h3{
                padding-bottom: 10px;
                font-size: 1.2rem;
            }
            .nav-pills .nav-link {
                min-height: 115px !important;
            }
            .card {
                padding: 0;
            }
        }
        #About{
            .numbers {
                width: 230px;
                height: 230px;
                margin: 40% auto 0 0;
            }
            .number{
                font-size: 4.5rem !important;
            }
            .col-4{
                max-width: 40%;
            }
            ul{
                margin-left: -9% !important;
            }
        }
        #Stages{
            .col-auto {
                width: 100% !important;
            }
            h3{
                font-size: 1.2rem;
                margin-bottom: 0.25rem;
            }
            h4{
                font-size: 1.15rem;
            }
            .card{
                padding: 0;
            }
            .nav-item, .flex-column li {
                width: 21%;
                margin: 2% 0 2% 4%;
                min-width: 18% !important;
            }
            .nav-item .nav-link {
                padding: 0.5rem 0.1rem !important;
                min-height: 150px !important;
            }
            .tab-content {
                height: 260px;
            }
            .card-body{
                line-height: 1.4rem;
                padding: 0.8rem;
            }
            .card-text li {
                border: none;
                margin-top: 1% !important;
            }
        }
        .slider{
            width: 50px;
        }
        #Customs{
            svg{
                width: 42px;
            }
        }
        #Calculation{
            .flex-container, button {
                width: 100%;
                margin-left: 0;
            }
            .flex-container{
                div {
                    width: 50%;
                    padding: 10px 0;
                    &:nth-child(2),&:nth-child(1),&:nth-child(3),&:nth-child(6),&:nth-child(7),&:nth-child(8){
                        width: 50%;
                    }
                    &:nth-child(2){
                        border-top-right-radius: 10px;
                    }
                    &:nth-child(5){
                        border-top-right-radius: 0;
                    }
                    &:nth-child(6){
                        border-bottom-left-radius: 0;
                    }
                    &:nth-child(9){
                        border-bottom-left-radius: 10px;
                    }
                    p{
                        margin-right: 0;
                        padding: 0.3rem;
                        font-size: 1rem
                    }
                }
            }
            .form-control {
                padding: .3rem;
                font-size: 1rem !important;
            }
        }
        #Package{
            .flex-container .row {
                width:54%;
            }
            .col{
                padding-right: 0 !important;
            }
        }
        #MyFooter{
            .flex-container .inf{
                width: 40%;
                .row{
                    width: 100%;
                }
                &:last-child{
                    width: 60%;
                }
            }
        }
    }
    @media screen and (min-width: 500px) and (max-width: 768px){
        h1{
            font-size: 1.95rem !important;
            line-height: 2.25rem;
            margin-bottom: 4% !important;
        }
        h2{
            font-size: 1.15rem !important;
            padding-top: 0 !important;
        }
        #About, #Calculation{
            h2{
                font-size: 1.25rem !important;
            }
        }
        .form-control, .btn, li{
            font-size: .9rem !important;
        }
        p{
            font-size: .9rem;
        }
        #Advantages, #Customs, #Package, #Types, #Stages, #About, #Calculation {
            padding: 35px 0 35px;
        }
        #Home{
            padding: 10px 0 40px;
            .row{
                flex-direction: column-reverse;
            }
            p{
                margin-bottom: 6% !important;
            }
            p,button, .btn {
                font-size: 1rem !important;
            }
            button{
                padding: 8px 35px !important;
            }
            .carousel{
                margin-left: 1%;
            }
            .carousel img {
                width: 100%;
                height: 220px;
            }
            .shadow{
                top: 10%;
                left: 13%;
                width: 83%;
                height: 97%;
                border: 3.6px solid #FF7A00;
            }
        }
        #Advantages{
            .number {
                font-size: 1.8rem;
                width: 50px;
                margin-bottom: 5%;
            }
            .col-2{
                max-width: 30%;
            }
            .col, .col-2{
                padding: 0 10px !important;
            }
            svg {
                width: 45px;
                padding: 0;
            }
            .text {
                height: 60px;
                margin-bottom: 0 !important;
            }
        }
        #Types{
            .col-auto {
                width: 100% !important;
            }
            .flex-column {
                flex-direction: row !important;
            }
            .nav-item, .flex-column li {
                width: 40%;
                margin: 2% 2% 2% 2%;
                min-width: 45% !important;
            }
            h3{
                padding-bottom: 10px;
                font-size: 1.2rem;
            }
            .nav-pills .nav-link {
                min-height: 100px !important;
            }
            .card {
                padding: 0;
                margin-top: -4%;
            }
            .card-body{
                padding: .8rem;
                height: 410px;
            }
            .tab-content{
                margin-top: 20px;
                margin-right: 20px;
            }
        }
        #About{
            .row{
                flex-direction: column-reverse;
            }
            h2{
                padding-bottom: 10px;
            }
            .numbers {
                width: 210px;
                height: 210px;
                padding: 10px;
                margin: 2% auto;
                display: block;
            }
            .number{
                font-size: 4rem !important;
            }
            .col{
                padding-right: 1rem !important;
            }
            .col-4{
                max-width: 100%;
            }
            li{
                margin-bottom: 1rem !important;
            }
            ul{
                margin-left: -5% !important;
                margin-right: 5%;
            }
        }
        #Stages{
            .col-auto {
                width: 100% !important;
            }
            h3{
                font-size: 1.2rem;
                margin-bottom: 0.25rem;
            }
            h4{
                font-size: 1.15rem;
            }
            .card{
                padding: 0;
            }
            .nav-item, .flex-column li {
                width: 42%;
                margin: 2% 4% 2% 4%;
                min-width: 42% !important;
            }
            .nav-item .nav-link {
                padding: 0.5rem 0.1rem !important;
                min-height: 160px !important;
            }
            .tab-content {
                height: 250px;
                margin-left: 4%;
                margin-right: 3%;
            }
            .card-body{
                line-height: 1.4rem;
                padding: 0.8rem;
            }
            .card-text li {
                border: none;
                margin-top: 1% !important;
            }
        }
        .slider{
            width: 50px;
        }
        #Customs{
            .carousel{
                display: block;
                width: 50%;
                margin: 0 auto;
            }
            .flex-container{
                display: none;
            }
            .flex-container div{
                width: 50%;
                padding: 0 15px;
            }
            h2{
                padding: 0 4%;
                &:before {
                    margin-left: -100%;
                    left: 5%;
                }
                &:after {
                    margin-right: -100%;
                    right: 5%;
                }
            }
            img{
                margin-top: 6%;
            }
            svg{
                width: 35px;
            }
        }
        #Calculation{
            .flex-container, button {
                width: 100%;
                margin-left: 0;
            }
            button{
                margin-top: 20px;
                padding: 10px 0;
            }
            .flex-container{
                div {
                    width: 50%;
                    padding: 5px 0;
                    &:nth-child(2),&:nth-child(1),&:nth-child(3),&:nth-child(6),&:nth-child(7),&:nth-child(8){
                        width: 50%;
                    }
                    &:nth-child(2){
                        border-top-right-radius: 10px;
                    }
                    &:nth-child(5){
                        border-top-right-radius: 0;
                    }
                    &:nth-child(6){
                        border-bottom-left-radius: 0;
                    }
                    &:nth-child(9){
                        border-bottom-left-radius: 10px;
                    }
                    p{
                        margin-right: 0;
                        padding: 0.3rem;
                        font-size: .9rem
                    }
                }
            }
            .form-control {
                padding: .3rem;
                font-size: .9rem !important;
            }
            svg{
                height: 10px;
                padding: 0;
            }
        }
        #Package{
            .flex-container .row {
                width:100%;
                padding: 7.5px 15px 7.5px;
            }
            .col{
                padding-right: 0 !important;
            }
            .col-4{
                max-width: 20%;
            }
        }
        #MyFooter{
            svg{
                width: 24px;
            }
            .flex-container .inf{
                width: 45%;
                .row{
                    width: 100%;
                }
                &:last-child{
                    width: 55%;
                }
            }
        }
    }
    @media screen and (min-width: 300px) and (max-width: 500px){
        h1{
            font-size: 1.55rem !important;
            line-height: 2.25rem;
            margin-bottom: 4% !important;
        }
        h2{
            font-size: 1.15rem !important;
            padding-top: 0 !important;
            color: #FF7A00;
            text-decoration: none;
             &:before, &:after{
                display: none !important;
            }
        }
        #Types h2, #Stages h2 {
            text-decoration: none;
            text-underline-offset: 1px;
            text-decoration-color: #FF7A00;
        }
        #About, #Calculation{
            h2{
                font-size: 1.25rem !important;
            }
        }
        .form-control, .btn, li{
            font-size: .9rem !important;
        }
        p{
            font-size: .9rem;
        }
        #Advantages, #Customs, #Package, #Types, #Stages, #About, #Calculation {
            padding: 25px 0 35px;
        }
        #Home{
            padding: 10px 0 40px;
            .row{
                flex-direction: column-reverse;
            }
            p{
                margin-bottom: 6% !important;
            }
            p,button, .btn {
                font-size: .9rem !important;
            }
            button{
                padding: 8px 35px !important;
            }
            .carousel{
                margin-left: 1%;
            }
            .carousel img {
                width: 100%;
                height: 200px;
            }
            .shadow{
                top: 7%;
                left: 13%;
                width: 83%;
                height: 97%;
                border: 3.5px solid #FF7A00;
            }
        }
        #Advantages{
            .row{
                flex-direction: column;
                margin: 0;
                .row{
                    flex-direction: row;
                    margin: 0;
                }
            }
            .number {
                font-size: 2.35rem;
                width: 60px;
                margin-bottom: 5%;
            }
            .col-2{
                max-width: 30%;
            }
            .col, .col-2{
                padding: 0 8px !important;
            }
            svg {
                width: 55px;
                padding: 0;
            }
            .text {
                height: 60px;
                margin-bottom: 0 !important;
            }
        }
        #Types{
            .col-auto {
                width: 100% !important;
            }
            .flex-column {
                flex-direction: row !important;
            }
            .nav-item, .flex-column li {
                width: 100%;
                margin: 2% 2% 2% 2%;
                min-width: 45% !important;
            }
            h3{
                padding-bottom: 10px;
                font-size: 1.2rem;
            }
            .nav-pills .nav-link {
                min-height: 65px !important;
            }
            .card {
                padding: 0;
                margin-top: -4%;
            }
            .card-body{
                padding: .8rem;
                height: 540px;
            }
            .tab-content{
                margin-top: 10px;
                margin-right: 5px;
            }
        }
        #About{
            .row{
                flex-direction: column-reverse;
            }
            h2{
                padding-bottom: 10px;
            }
            .numbers {
                width: 210px;
                height: 210px;
                padding: 10px;
                margin: 2% auto;
                display: block;
            }
            .number{
                font-size: 4rem !important;
            }
            .col{
                padding-right: 1rem !important;
            }
            .col-4{
                max-width: 100%;
            }
            li{
                margin-bottom: 1rem !important;
            }
            ul{
                margin-left: -5% !important;
                margin-right: 5%;
            }
        }
        #Stages{
            .col-auto {
                width: 100% !important;
            }
            h3{
                font-size: 1.15rem;
                margin-bottom: 0.25rem;
            }
            h4{
                font-size: 1.1rem;
            }
            .card{
                padding: 0;
            }
            .nav-item, .flex-column li {
                width: 46%;
                margin: 2% 2% 2% 2%;
                min-width: 42% !important;
            }
            .nav-item .nav-link {
                padding: 0.5rem 0.1rem !important;
                min-height: 130px !important;
            }
            .tab-content {
                height: 400px;
                margin-left: 4%;
                margin-right: 3%;
            }
            .card-body{
                line-height: 1.4rem;
                padding: 0.8rem;
            }
            .card-text li {
                border: none;
                margin-top: 1% !important;
            }
        }
        .slider{
            width: 50px;
        }
        #Customs{
            .carousel{
                display: block;
                width: 70%;
                margin: 0 auto;
            }
            .flex-container{
                display: none;
            }
            .flex-container div{
                width: 50%;
                padding: 0 15px;
            }
            h2{
                padding: 0;
                &:before {
                    margin-left: -100%;
                    left: 5%;
                }
                &:after {
                    margin-right: -100%;
                    right: 5%;
                }
            }
            img{
                margin-top: 6%;
            }
            svg{
                width: 35px;
            }
        }
        #Calculation{
            .flex-container, button {
                width: 100%;
                margin-left: 0;
            }
            button{
                margin-top: 20px;
                padding: 10px 0;
            }
            .flex-container{
                div {
                    width: 100%;
                    padding: 5px 0;
                    &:nth-child(2),&:nth-child(1),&:nth-child(3),&:nth-child(6),&:nth-child(7),&:nth-child(8){
                        width: 100%;
                    }
                    &:nth-child(1){
                        border-top-right-radius: 10px;
                    }
                    &:nth-child(5){
                        border-top-right-radius: 0;
                    }
                    &:nth-child(6){
                        border-bottom-left-radius: 0;
                    }
                    &:nth-child(10){
                        border-bottom-left-radius: 10px;
                    }
                    p{
                        margin-right: 0;
                        padding: 0.3rem;
                        font-size: .9rem;
                    }
                }
            }
            .form-control {
                padding: .3rem;
                height: auto;
                font-size: .9rem !important;
                margin-bottom: 0 !important;
            }
            svg{
                width: 100px;
                height: 10px;
                padding: 0;
            }
        }
        #Package{
            img{
                width: 120%;
            }
            .flex-container .row {
                width: 108%;
                padding: 7.5px 15px 7.5px;
            }
            .col-4{
                max-width: 28%;
            }
            .col{
                padding-right: 0 !important;
            }
        }
        #MyFooter{
            svg{
                width: 20px;
            }
            .flex-container .inf{
                width: 100%;
                .row{
                    margin-bottom: 4%;
                }
                br{
                    display: none;
                }
                &:last-child{
                    p{
                        margin-bottom: 4% !important;
                    }
                }
            }
        }
    }
    @media screen and (max-width: 300px){
        .navbar-brand svg{
            width: 75%;
        }
        h1{
            font-size: 1.35rem !important;
            line-height: 2.25rem;
            margin-bottom: 4% !important;
        }
        h2{
            font-size: 1.15rem !important;
            padding-top: 0 !important;
            color: #FF7A00;
            text-decoration: none;
            &:before, &:after{
                display: none !important;
            }
        }
        #Types h2, #Stages h2 {
            text-decoration: none;
            text-underline-offset: 1px;
            text-decoration-color: #FF7A00;
        }
        #About, #Calculation{
            h2{
                font-size: 1.25rem !important;
            }
        }
        .form-control, .btn, li{
            font-size: .85rem !important;
        }
        p{
            font-size: .85rem;
        }
        #Advantages, #Customs, #Package, #Types, #Stages, #About, #Calculation {
            padding: 25px 0;
        }
        #Home{
            padding: 10px 0 40px;
            .row{
                flex-direction: column-reverse;
            }
            p{
                margin-bottom: 6% !important;
            }
            p,button, .btn {
                font-size: .9rem !important;
            }
            button{
                padding: 8px 35px !important;
            }
            .carousel{
                margin-left: 1%;
            }
            .carousel img {
                width: 100%;
                height: 150px;
            }
            .shadow{
                top: 7%;
                left: 13%;
                width: 83%;
                height: 97%;
                border: 3px solid #FF7A00;
            }
        }
        #Advantages{
            .row{
                flex-direction: column;
                margin: 0;
                .row{
                    flex-direction: row;
                    margin: 0;
                }
            }
            .number {
                font-size: 2rem;
                width: 50px;
                margin-left: -5%;
                margin-bottom: 5%;
            }
            .col-2{
                max-width: 30%;
            }
            .col, .col-2{
                padding: 0 5px !important;
            }
            svg {
                width: 50px;
                margin-left: -5%;
                padding: 0;
            }
            .text {
                height: 60px;
                margin-bottom: 0 !important;
            }
        }
        #Types{
            .col-auto {
                width: 100% !important;
            }
            .flex-column {
                flex-direction: row !important;
            }
            .nav-item, .flex-column li {
                width: 100%;
                margin: 2% 2% 2% 2%;
                min-width: 45% !important;
            }
            h3{
                padding-bottom: 10px;
                font-size: 1.15rem;
            }
            .nav-pills .nav-link {
                min-height: 65px !important;
            }
            .card {
                padding: 0;
                margin-top: -4%;
            }
            .card-body{
                padding: .8rem;
                height: max-content;
                ul{
                    margin-left: -8.5%;
                }
            }
            .tab-content{
                margin-top: 10px;
                width: 93%;
            }
        }
        #About{
            .row{
                flex-direction: column-reverse;
            }
            h2{
                padding-bottom: 10px;
            }
            .numbers {
                width: 180px;
                height: 180px;
                padding: 10px;
                margin: 2% auto;
                display: block;
                p{
                    margin-bottom: 0 !important;
                }
            }
            .number{
                font-size: 3.5rem !important;
                margin-bottom: 0 !important;
            }
            .col{
                padding-right: 1rem !important;
            }
            .col-4{
                max-width: 100%;
            }
            li{
                margin-bottom: 1rem !important;
            }
            ul{
                margin-left: -18% !important;
                margin-right: 5%;
            }
        }
        #Stages{
            .col-auto {
                width: 100% !important;
            }
            h3{
                font-size: 1.2rem;
                margin-bottom: 0.25rem;
            }
            h4{
                font-size: 1.1rem;
            }
            .card{
                padding: 0;
                ol{
                    margin-left: -8.5%;
                }
            }
            .nav-item, .flex-column li {
                width: 90%;
                margin: 2% 2% 2% 8%;
                min-width: 42% !important;
            }
            .nav-item .nav-link {
                padding: 0.5rem 0.1rem !important;
                min-height: 130px !important;
            }
            .tab-content {
                height: max-content;
                margin-left: 4%;
                margin-right: 3%;
            }
            .card-body{
                line-height: 1.4rem;
                padding: 0.8rem;
            }
            .card-text li {
                border: none;
                margin-top: 1% !important;
            }
        }
        .slider{
            width: 50px;
        }
        #Customs{
            .carousel{
                display: block;
                width: 90%;
                margin: 0 auto;
            }
            .flex-container{
                display: none;
            }
            .flex-container div{
                width: 50%;
                padding: 0 15px;
            }
            h2{
                padding: 0;
                &:before {
                    margin-left: -100%;
                    left: 5%;
                }
                &:after {
                    margin-right: -100%;
                    right: 5%;
                }
            }
            img{
                margin-top: 6%;
            }
            svg{
                width: 35px;
            }
        }
        #Calculation{
            .flex-container, button {
                width: 100%;
                margin-left: 0;
            }
            button{
                margin-top: 20px;
                padding: 10px 0;
            }
            svg{
                display: none;
            }
            .flex-container{
                div {
                    width: 100%;
                    padding: 5px 0;
                    &:nth-child(2),&:nth-child(1),&:nth-child(3),&:nth-child(6),&:nth-child(7),&:nth-child(8){
                        width: 100%;
                    }
                    &:nth-child(1){
                        border-top-right-radius: 10px;
                    }
                    &:nth-child(5){
                        border-top-right-radius: 0;
                    }
                    &:nth-child(6){
                        border-bottom-left-radius: 0;
                    }
                    &:nth-child(10){
                        border-bottom-left-radius: 10px;
                    }
                    p{
                        margin-right: 0;
                        padding: 0.3rem;
                        font-size: .9rem;
                    }
                }
            }
            .form-control {
                padding: .3rem;
                height: auto;
                font-size: .9rem !important;
                margin-bottom: 0 !important;
            }
            svg{
                width: 100px;
                height: 10px;
                padding: 0;
            }
        }
        #Package{
            img{
                width: 90%;
                margin-bottom: 4%;
            }
            .flex-container .row {
                width: 110%;
                padding: 7.5px 15px 7.5px;
                flex-direction: column;
            }
            .col-4{
                max-width: 60%;
            }
            .col{
                padding-right: 0 !important;
            }
        }
        #MyFooter{
            svg{
                width: 20px;
            }
            .flex-container .inf{
                width: 100%;
                .row{
                    margin-bottom: 4%;
                }
                br{
                    display: none;
                }
                &:last-child{
                    p{
                        margin-bottom: 4% !important;
                    }
                }
            }
        }
    }
</style>

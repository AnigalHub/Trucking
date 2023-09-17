<template>
  <div id="app">
      <Navbar/>
      <Home/>
      <Advantages/>
      <Types/>
      <About/>
      <Stages/>
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
    import Calculation from "@/components/Calculation";
    import Package from "@/components/Package";
    import MyFooter from "@/components/MyFooter";
    export default {
        name: 'App',
        components: {
            MyFooter,
            Package,
            Calculation,
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
    /*индикаторы карусели (слева, справа)*/
    #About .carousel-indicators{
        display: none !important;
    }
</style>
<style lang="scss">
    $colorText: white;
    $colorImportant: #FF7A00;
    $colorBody: #010101;

    /*картинка в модальном окне*/
    .modal-dialog img{
        width: 100% !important;
        box-shadow: none !important;
    }
    /*"крестик" (размер) - кнопка закрытия модального окна*/
    .close{
        font-size: 2rem !important;
        padding: 1rem .5rem !important;
        color: $colorText !important;
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
    .modal-body{padding: 0 1rem 1rem 1rem!important;}
    /*footer-модального окна*/
    .modal-footer{display: none !important;}
    @media (min-width: 992px){
        /*ширина модального окна на разных экранах*/
        .modal-lg, .modal-xl{max-width: 720px !important;}
    }
    /*миксин*/
    @mixin h2Underline{
        text-decoration: underline;
        text-underline-offset: 10px;
        text-decoration-color: $colorImportant;
    }
    body{
        background: $colorBody !important;
    }
    /*вся страница*/
    #app{
        height: 100%;
        margin: 0 !important;
        padding: 0 !important;
        background: $colorBody;
        color: $colorText;
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
    /*картинки*/
    img{
        width: 100%;
    }
    /*заголовки*/
    h1{
        margin-top: 40px !important;
        margin-bottom: 30px !important;
        font-size: 2.3rem !important;
        line-height: 3.8rem;
        text-transform: uppercase;
        color: $colorImportant;
    }
    h2{
        padding-top: 30px;
        padding-bottom: 30px;
        font-weight: 400 !important;
        letter-spacing: 1.5px;
        font-size: 1.7rem !important;
        color: $colorText;
        text-transform: uppercase;
        text-align: center;
    }
    h3{
        color: $colorImportant;
        text-align: center;
        padding-bottom: 15px;
    }
    /*компоненты - Премущества, Упаковка*/
    #Advantages, #Package{
        /*заголовки*/
        h2{
            overflow: hidden;
            text-align: center;
            span {
                display: inline-block;
                vertical-align: middle;
            }
            /*заголовки (до, после)*/
            &:before, &:after {
                content: "";
                display: inline-block;
                vertical-align: middle;
                width: 20%;
                height: 2px;
                background-color: $colorImportant;
                position: relative;
            }
            /*заголовки (до)*/
            &:before {
                margin-left: -100%;
                left: -25%;
            }
            /*заголовки (после)*/
            &:after {
                margin-right: -100%;
                right: -25%;
            }
        }
    }
    /*компоненты - Виды, Этапы (заголовки)*/
    #Types h2, #Stages h2{
        /*миксин*/
        @include h2Underline;
    }
    /*компоненты - О нас, Калькулятор (заголовки)*/
    #About h2, #Calculation h2{
        color: $colorImportant;
        font-size: 2.5rem !important;
    }
    /*параграф, форма, кнопки, списки (текст)*/
    p, .form-control, .btn, li{
        font-family: "Montserrat", sans-serif;
        font-size: 1.1rem;
        font-weight: 400 !important;
        margin-bottom: .5rem !important;
    }
    /*ссылки*/
    a{
        color: $colorText !important;
        text-decoration: none;
        /*при наведении*/
        &:hover{
            color: $colorText;
        }
    }
    /*кнопки*/
    .btn{
        font-size: 1.35rem !important;
    }
    button{
        color: $colorText;
        text-align: center;
    }
    /*формы*/
    .form-control{
        font-size: 1.1rem !important;
    }
    /*текст в инпуте(форме)*/
    input::placeholder{
        color: rgba(255, 255, 255, 0.5) !important;
    }
    /*компонент - Премущества*/
    #Advantages{
        background: url("../public/bgAd.png") no-repeat;
    }
    /*компонент - О нас*/
    #About{
        background: url("../public/bgAbout.png") no-repeat;
    }
    /*компонент - Упаковка*/
    #Package{
        background: url("../public/bgPack.jpg") no-repeat;
    }
    /*компонент - Преимущества, О нас, Упаковка*/
    #Advantages, #About, #Package{
        background-size: 100% 100%;
    }
    /*компонент - Преимущества, О нас, Упаковка, Виды, Этапы, Калькулятор*/
    #Advantages, #About, #Package, #Types, #Stages, #Calculation{
        padding: 15px 0 50px;
    }
    /*блок под переключатель*/
    .custom-switch{
        width: 100% !important;
    }
    /*блок-переключатель*/
    .custom-control{
        padding: 0 !important;
        border: none !important;
    }
    /*метка*/
    label{
        display: inline !important;
        margin-left: 40px !important;
        margin-bottom: 0.5rem !important;
    }
    /*блок-переключатель (активный)*/
    .custom-control-input:checked ~ .custom-control-label::before{
        border-color: rgba(255, 122, 0, 0.45) !important;
        background-color: rgba(255, 122, 0, 0.45) !important;
    }
    /*блок-переключатель*/
    .custom-switch .custom-control-label::before{
        transform: scale(1.05, 1);
    }
    /*блок-карточка*/
    .card{
        padding: 0 3.25rem;
        background: transparent !important;
    }
    /*блок-карточка (название)*/
    .card-header{
        padding: 0 !important;
    }
    /*блок-карточка (текст, список)*/
    .card-text li{
        border: none;
        margin-top: 4% !important;
    }
    /*компоненты -  Виды, Этапы*/
    #Types, #Stages{
        /*блоки-табов-выбора*/
        .nav-pills .nav-link {
            display: flex;
            color: $colorText;
        }
        /*блок-таба-выбора*/
        .nav-item{
            border: 2px solid rgba(255, 122, 0, 0.6);
            border-radius: 5px;
            /*блок-таба-выбора (ссылка)*/
            .nav-link{
                background-size: 100% 100% !important;
            }
        }
        /*блок-таба-контент*/
        .tab-content{
            margin-left: 10px;
            border: 2px solid rgba(255, 122, 0, 0.37);
        }
    }
    /*компонент -  Главная*/
    #Home{
        padding: 20px 0 100px;
        /*список*/
        ul{
            margin: 30px 0 !important;
            list-style: none;
        }
        /*пункты списка*/
        li{
            margin: 25px 0 !important;
            color: $colorText;
            font-size: 1.5rem !important;
            line-height: 2.4rem;
        }
        /*пункты списка*/
        ul > li{
            position: relative;
            margin: 10px;
            /*пункты списка(сами пункты)*/
            &:before{
                content: '✔';
                position: absolute;
                left: -40px;
                text-shadow: 1.5px 1.5px 1.5px #714828;
                color: #908989 !important;
            }
        }
        /*параграф*/
        p{
            font-size: 1.45rem;
            margin-bottom: 8% !important;
        }
        /*карусель*/
        .carousel {
            margin-top: 10%;
            width: 95%;
            /*пункты списка*/
            li{
                margin: 3.5px !important;
            }
            /*картинки*/
            img{
                height: 400px;
            }
        }
        /*тень картинки (квадрат)*/
        .shadow{
            position: absolute;
            border: 4.5px solid $colorImportant;
            top: 5%;
            left: 9%;
            height: 102%;
            width: 88%;
        }
        /*кнопки*/
        button{
            background: transparent;
            padding: 8px 85px !important;
            border-radius: 10px;
            font-size: 1.2rem;
            border: 2px solid $colorImportant;
            z-index: 10;
            position: relative;
        }
    }
    /*компонент - Преимущества*/
    #Advantages{
        /*цифры*/
        .number{
            color: $colorImportant;
            font-size: 3.65rem;
            text-align: center;
            transform: scale(1.2, 1.2);
        }
        /*описание*/
        .descr{
            color: $colorImportant;
            text-align: center;
            margin-top: -15%;
        }
        /*текст*/
        .text{
            display: flex;
            height: 105px;
            align-items: center;
        }
        /*сетка бутстрап*/
        .col-2{
            padding: 0 !important;
        }
        /*сетка бутстрап*/
        .col{
            padding: 0 25px !important;
        }
        /*svg*/
        svg{
            padding: 8px;
        }
    }
    /*компоненты -  Виды*/
    #Types{
        /*блоки-табов-выбора*/
        .nav-pills .nav-link {
            min-height: 120px;
            justify-content: center;
            align-items: center;
        }
        /*блок-таба-выбора (ссылка - активная)*/
        .nav-pills .nav-link.active{
            color: $colorImportant !important;
            filter: contrast(90%) brightness(150%);
        }
        /*блок-таба-контент*/
        .tab-content{
            background: url("../public/types/bg.jpg");
            border-radius: 5px;
        }
        /*блок-таба-выбора*/
        .nav-item{
            margin: 0 0 5px;
            text-align: center;
            /*блок-таба-выбора - первый*/
            &:nth-child(1) .nav-link{
                background: url("../public/types/air.jpg");
            }
            /*блок-таба-выбора - второй*/
            &:nth-child(2) .nav-link{
                background: url("../public/types/auto.jpg");
            }
            /*блок-таба-выбора - третий*/
            &:nth-child(3) .nav-link{
                background: url("../public/types/train.jpg");
            }
            /*блок-таба-выбора - четвертый*/
            &:nth-child(4) .nav-link{
                background: url("../public/types/ship.jpg");
            }
        }
    }
    /*компонент - О нас*/
    #About{
        /*пункты списка*/
        li{
            list-style-type:none;
            border-bottom: 2px solid rgba(255, 122, 0, 0.5);
            margin-bottom: 1.5rem !important;
        }
        /*параграф*/
        p{
            text-align: center;
        }
        /*цифры*/
        .number{
            color: $colorImportant;
            font-size: 6rem;
            text-align: center;
            transform: scale(1.2, 1.2);
        }
        /*блок под цифры*/
        .numbers{
            border-radius: 50%;
            width: 300px;
            height: 300px;
            padding: 20px 20px 0;
            margin: 28% auto 0 10%;
            border: 2px solid rgba(255, 122, 0, 0.5);
        }
        /*сетка бутстрап*/
        .col{
            padding-right: 4rem !important;
        }
    }
    /*компонент - Этапы*/
    #Stages{
        /*блок-таба-выбора (ссылка)*/
        .nav-link{
            margin: -6% 6% 6% -8%;
        }
        /*сетка бутстрап*/
        .col-auto {
            width: 60% !important;
        }
        /*блок-контент*/
        .flex-column{
            display: contents !important;
            /*пункты списка*/
            li{
                width: 40%;
                float: left;
            }
        }
        /*блоки-табов-выбора*/
        .nav-pills .nav-link {
            align-items: end;
        }
        /*блок-таба-выбора (ссылка - активная)*/
        .nav-pills .nav-link.active{
            color: #8e4404 !important;
            filter: contrast(90%) brightness(190%);
            font-weight: 600 !important;
            border: 1px solid rgba(255, 122, 0, 0.37);
        }
        /*блок-таба-контент*/
        .tab-content{
            background: #1C1D1E;
            margin-top: 1%;
            height: 500px;
            border-radius: 5px;
        }
        /*блок-таба-выбора*/
        .nav-item{
            min-width: 40%;
            margin: 4%;
            /*блок-таба-выбора*/
            .nav-link{
                min-height: 220px !important;
            }
            /*блок-таба-выбора - первый*/
            &:nth-child(1) .nav-link{
                background: url("../public/stages/receiving.png");
            }
            /*блок-таба-выбора - второй*/
            &:nth-child(2) .nav-link{
                background: url("../public/stages/delivery.png");
            }
            /*блок-таба-выбора - третий*/
            &:nth-child(3) .nav-link{
                background: url("../public/stages/customs.png");
            }
            /*блок-таба-выбора - четвертый*/
            &:nth-child(4) .nav-link{
                background: url("../public/stages/tothedoor.png");
            }
        }
        /*блок-карточка (заголовок)*/
        .card-text h4{
            text-align: center;
            font-weight: 700 !important;
            margin-top: -3%;
        }
    }
    /*компонент - Калькулятор*/
    #Calculation{
        /*заголовки*/
        h2{
          padding-top: 0 !important;
        }
        /*контейнер, который включает в себя повтор блоков*/
        .flex-container {
            width: 105%;
            margin-left: -2.5%;
            /*блоки*/
            div{
                border: .25px solid rgba(255, 122, 0, 0.45);
                background: #1F1E1E;
                width: 17%;
                padding: 15px 0;
                /*блоки (первый)*/
                &:first-child{
                    border-top-left-radius: 10px 10px;
                }
                /*блоки (второй,первый, шестой, седьмой, третий, восьмой)*/
                &:nth-child(2),&:nth-child(1),&:nth-child(6),&:nth-child(7), &:nth-child(3),&:nth-child(8){
                    width: 21.5%;
                }
                /*блоки (пятый)*/
                &:nth-child(5){
                    border-top-right-radius: 10px 10px;
                }
                /*блоки (шестой)*/
                &:nth-child(6){
                    border-bottom-left-radius: 10px 10px;
                }
                /*блоки (последний)*/
                &:last-child{
                    border-bottom-right-radius: 10px 10px;
                }
                /*параграф*/
                p{
                    color: rgba(255, 255, 255, 0.5) !important;
                    float: left;
                    font-size: 1.1rem;
                    padding: 0.375rem 15px;
                }
            }
        }
        /*кнопки*/
        button{
            margin-top: 30px;
            border-radius: 10px;
            width: 103.5%;
            margin-left: -2.5%;
            background: rgba(255, 122, 0, 0.2);
            padding: 15px 0;
            border: .25px solid rgba(255, 122, 0, 0.45);
        }
        /*форма*/
        .form-control{
            color: $colorText;
            background: transparent;
            border: none;
        }
        /*svg*/
        svg{
            padding-left: 15px;
        }
    }
    /*компонент - Упаковка*/
    #Package{
        /*контейнер, который включает в себя повтор блоков*/
        .flex-container {
            /*сетка бутстрап*/
            .row{
                width: 49%;
                padding: 15px;
            }
            /*названия*/
            .name{
                /*миксин*/
                @include h2Underline;
            }
        }
    }
    /*компонент - Футер*/
    #MyFooter{
        padding: 40px 0 10px;
        /*контейнер, который включает в себя повтор блоков*/
        .flex-container .inf{
            width: 50%;
            margin-bottom: 2%;
        }
        /*svg*/
        svg{
            width: 30px;
        }
    }



    /*АДАПТИВНОСТЬ*/
    @media screen and (min-width: 992px) and (max-width: 1200px){
        /*заголовки*/
        h1{
            margin: 20px 0 !important;
            font-size: 1.9rem !important;
            line-height: 3rem;
        }
        /*компоненты - О нас, Калькулятор (заголовки)*/
        #About h2, #Calculation h2{
            font-size: 2rem !important;
        }
        /*форма, кнопки, списки (текст)*/
        .form-control, .btn, li{
            font-size: 1.15rem !important;
        }
        /*параграф*/
        p{
            font-size: 1.15rem;
        }
        /*компонент - Преимущества, О нас, Упаковка, Виды, Этапы, Калькулятор*/
        #Advantages, #About, #Package, #Types, #Stages, #Calculation {
            padding: 15px 0 40px;
        }
        /*компонент - Главная*/
        #Home{
            padding: 0 0 70px;
            /*список*/
            ul{
                margin: 35px 0 !important;
            }
            /*пункты списка*/
            li{
                margin: 20px 0 !important;
                font-size: 1.3rem !important;
                line-height: 2rem;
            }
            /*параграф, кнопки*/
            p, button, .btn {
                font-size: 1.25rem !important;
            }
            /*картинки в карусели*/
            .carousel img {
                height: 340px;
           }
        }
        /*компонент - Преимущества*/
        #Advantages{
            /*цифры*/
           .number{
               font-size: 3.2rem;
           }
           /*svg*/
           svg{
               padding: 5px;
           }
        }
        /*компоненты -  Виды*/
        #Types{
            /*заголовки*/
            h3{
                padding-bottom: 10px;
                font-size: 1.5rem;
            }
            /*блоки-табов-выбора*/
            .nav-pills .nav-link{
                height: 100px !important;
            }
            /*блок-карточка*/
            .card{
                padding: 0 2rem;
            }
            /*блок-карточка-тело*/
            .card-body{
                line-height: 1.6rem;
            }
        }
        /*компонент - О нас*/
        #About{
            /*блок под цифры*/
            .numbers{
                width: 285px;
                height: 285px;
                margin: 28% auto 0 1%;
            }
        }
        /*компонент - Этапы*/
        #Stages{
           /*заголовки*/
           h3{
               font-size: 1.4rem;
               margin-bottom: 0;
           }
           h4{
               font-size: 1.2rem;
           }
           /*блоки-табов-выбора*/
           .nav-item .nav-link{
               min-height: 200px !important;
           }
           /*блок-таба-контент*/
           .tab-content{
                height: 450px;
           }
           /*блок-карточка (тело)*/
           .card-body{
               line-height: 1.4rem;
           }
        }
        /*компонент - Калькулятор*/
        #Calculation{
            /*контейнер, который включает в себя повтор блоков, кнопки*/
            .flex-container, button{
                width: 100%;
                margin-left: 0;
            }
            /*контейнер, который включает в себя повтор блоков*/
            .flex-container{
                /*блоки*/
                div{
                    width: 19.5%;
                    padding: 10px 0;
                    /*блоки (второй, первый, шестой, седьмой)*/
                    &:nth-child(2),&:nth-child(1),&:nth-child(6),&:nth-child(7){
                        width: 19.5%;
                    }
                    /*параграф*/
                    p{
                        margin-right: 0;
                        padding: 0.3rem;
                        font-size: 1rem
                    }
                }
            }
            /*форма*/
            .form-control{
                padding: .3rem;
                font-size: 1rem !important;
            }
        }
        /*компонент - Упаковка*/
        #Package{
            /*сетка бутстрап*/
            .col{
                padding-right: 0 !important;
            }
        }
        /*компонент - Футер*/
        #MyFooter{
            /*контейнер, который включает в себя повтор блоков*/
            .flex-container .inf{
                width: 40%;
                /*сетка бутстрап*/
                .row{
                    width: 100%;
                }
            }
        }
    }
    @media screen and (min-width: 768px) and (max-width: 992px){
        /*заголовки*/
        h1{
            margin: 20px 0 !important;
            font-size: 1.4rem !important;
            line-height: 2.5rem;
        }
        h2{
          font-size: 1.35rem !important;
        }
        /*компоненты - О нас, Калькулятор (заголовки)*/
        #About h2, #Calculation h2{
            font-size: 1.4rem !important;
        }
        /*форма, кнопки, списки (текст)*/
        .form-control, .btn, li{
            font-size: 1rem !important;
        }
        /*параграф*/
        p{
            font-size: 1rem;
        }
        /*компонент - Преимущества, О нас, Упаковка, Виды, Этапы, Калькулятор*/
        #Advantages, #About, #Package, #Types, #Stages, #Calculation{
            padding: 15px 0 45px;
        }
        /*компонент - Главная*/
        #Home{
            padding: 0 0 50px;
            /*список*/
            ul{
                margin: 25px 0 !important;
            }
            /*пункты списка*/
            li{
                margin: 10px 0 !important;
                font-size: 1.1rem !important;
                line-height: 1.7rem;
            }
            /*параграф, кнопки*/
            p, button, .btn{
                font-size: 1rem !important;
            }
            /*картинки в карусели*/
            .carousel img{
                height: 260px;
            }
            /*тень картинки (квадрат)*/
            .shadow{
                height: 99%;
            }
        }
        /*компонент - Преимущества*/
        #Advantages{
            /*цифры*/
            .number{
                font-size: 2.35rem;
            }
            /*svg*/
            svg{
                padding: 0;
            }
            /*текст*/
            .text{
                height: 80px;
            }
        }
        /*компоненты -  Виды*/
        #Types{
            /*сетка бутстрап*/
            .col-auto{
                width: 40% !important;
            }
            /*заголовки*/
            h3{
                padding-bottom: 10px;
                font-size: 1.2rem;
            }
            /*блоки-табов-выбора*/
            .nav-pills .nav-link{
                min-height: 115px !important;
            }
            /*блок-карточка*/
            .card {
                padding: 0;
            }
        }
        /*компонент - О нас*/
        #About{
            /*блок под цифры*/
            .numbers{
                width: 230px;
                height: 230px;
                margin: 40% auto 0 0;
            }
            /*цифры*/
            .number{
                font-size: 4.5rem !important;
            }
            /*сетка бутстрап*/
            .col-4{
                max-width: 40%;
            }
            /*список*/
            ul{
                margin-left: -9% !important;
            }
        }
        /*компонент - Этапы*/
        #Stages{
            /*сетка бутстрап*/
            .col-auto{
                width: 100% !important;
            }
            /*заголовкм*/
            h3{
                font-size: 1.2rem;
                margin-bottom: 0.25rem;
            }
            h4{
                font-size: 1.15rem;
            }
            /*блок-карточка*/
            .card{
                padding: 0;
            }
            /*блок-таба-выбора, список*/
            .nav-item, .flex-column li{
                width: 21%;
                margin: 2% 0 2% 4%;
                min-width: 18% !important;
            }
            /*блок-таба-выбора*/
            .nav-item .nav-link{
                padding: 0.5rem 0.1rem !important;
                min-height: 150px !important;
            }
            /*блок-таба-контент*/
            .tab-content{
                height: 275px;
            }
            /*блок-карточка (тело)*/
            .card-body{
                line-height: 1.4rem;
                padding: 0.8rem;
            }
            /*блок-карточка (текст, список)*/
            .card-text li{
                border: none;
                margin-top: 1% !important;
            }
        }
        /*компонент - Калькулятор*/
        #Calculation{
            /*контейнер, который включает в себя повтор блоков, кнопки*/
            .flex-container, button{
                width: 100%;
                margin-left: 0;
            }
            /*контейнер, который включает в себя повтор блоков*/
            .flex-container{
                /*блоки*/
                div{
                    width: 50%;
                    padding: 10px 0;
                    /*блоки (второй,первый, шестой, седьмой, третий, восьмой)*/
                    &:nth-child(2),&:nth-child(1),&:nth-child(3),&:nth-child(6),&:nth-child(7),&:nth-child(8){
                        width: 50%;
                    }
                    /*блоки (второй)*/
                    &:nth-child(2){
                        border-top-right-radius: 10px;
                    }
                    /*блоки (пятый)*/
                    &:nth-child(5){
                        border-top-right-radius: 0;
                    }
                    /*блоки (шестой)*/
                    &:nth-child(6){
                        border-bottom-left-radius: 0;
                    }
                    /*блоки (девятый)*/
                    &:nth-child(9){
                        border-bottom-left-radius: 10px;
                    }
                    /*параграф*/
                    p{
                        margin-right: 0;
                        padding: 0.3rem;
                        font-size: 1rem
                    }
                }
            }
            /*форма*/
            .form-control{
                padding: .3rem;
                font-size: 1rem !important;
            }
        }
        /*компонент - Упаковка*/
        #Package{
            /*контейнер, который включает в себя повтор блоков*/
            .flex-container .row{
                width:54%;
            }
            /*сетка бутстрап*/
            .col{
                padding-right: 0 !important;
            }
        }
        /*компонент - Футер*/
        #MyFooter{
            /*контейнер, который включает в себя повтор блоков*/
            .flex-container .inf{
                width: 40%;
                /*сетка бутстрап*/
                .row{
                    width: 100%;
                }
                /*последний блок*/
                &:last-child{
                    width: 60%;
                }
            }
        }
    }
    @media screen and (min-width: 500px) and (max-width: 768px){
        /*заголовки*/
        h1{
            margin: 25px 0 0 !important;
            font-size: 1.5rem !important;
            line-height: 2.25rem;
        }
        h2{
            font-size: 1.15rem !important;
            padding-top: 0 !important;
        }
        /*компоненты - О нас, Калькулятор (заголовки)*/
        #About h2, #Calculation h2{
            font-size: 1.25rem !important;
        }
        /*форма, кнопки, списки (текст)*/
        .form-control, .btn, li{
            font-size: .9rem !important;
        }
        /*параграф*/
        p{
            font-size: .9rem;
        }
        /*компонент - Преимущества, О нас, Упаковка, Виды, Этапы, Калькулятор*/
        #Advantages,  #About, #Package, #Types, #Stages, #Calculation{
            padding: 25px 0;
        }
        /*компонент - Главная*/
        #Home{
            padding: 0 0 20px;
            /*список*/
            ul{
                margin: 20px 0 20px !important;
            }
            /*пункты списка*/
            li{
                margin: 10px 0 !important;
                font-size: 1rem !important;
                line-height: 1.4rem;
            }
            /*сетка бутстрап*/
            .row{
                flex-direction: column-reverse;
            }
            /*параграф*/
            p{
                margin-bottom: 6% !important;
            }
            /*параграф, кнопки*/
            p, button, .btn{
                font-size: 1rem !important;
            }
            /*кнопки*/
            button{
                padding: 8px 35px !important;
            }
            /*карусель*/
            .carousel{
                margin-left: 1%;
            }
            /*картинки в карусели*/
            .carousel img {
                width: 100%;
                height: 220px;
            }
            /*тень картинки (квадрат)*/
            .shadow{
                top: 10%;
                left: 13%;
                width: 83%;
                height: 97%;
                border: 3.6px solid $colorImportant;
            }
        }
        /*компонент - Преимущества*/
        #Advantages{
            /*цифры*/
            .number{
                font-size: 1.8rem;
                width: 50px;
                margin-bottom: 5%;
            }
            /*сетка бутстрап*/
            .col-2{
                max-width: 30%;
            }
            /*сетка бутстрап*/
            .col, .col-2{
                padding: 0 10px !important;
            }
            /*svg*/
            svg{
                width: 45px;
                padding: 0;
            }
            /*текст*/
            .text{
                height: 60px;
                margin-bottom: 0 !important;
            }
        }
        /*компоненты -  Виды*/
        #Types{
            /*сетка бутстрап*/
            .col-auto{
                width: 100% !important;
            }
            /*блок-контент*/
            .flex-column{
                flex-direction: row !important;
            }
            /*блок-таба-выбора, список*/
            .nav-item, .flex-column li{
                width: 40%;
                margin: 2% 2% 2% 2%;
                min-width: 45% !important;
            }
            /*заголовки*/
            h3{
                padding-bottom: 10px;
                font-size: 1.2rem;
            }
            /*блоки-табов-выбора*/
            .nav-pills .nav-link{
                min-height: 100px !important;
            }
            /*блок-карточка*/
            .card{
                padding: 0;
                margin-top: -4%;
            }
            /*блок-карточка-тело*/
            .card-body{
                padding: .8rem;
                height: 380px;
                line-height: 1.2rem;
            }
            /*блок-таба-контент*/
            .tab-content{
                margin-top: 20px;
                margin-right: 20px;
            }
        }
        /*компонент - О нас*/
        #About{
            /*сетка бутстрап*/
            .row{
                flex-direction: column-reverse;
            }
            /*заголовки*/
            h2{
                padding-bottom: 10px;
            }
            /*блок под цифры*/
            .numbers{
                width: 210px;
                height: 210px;
                padding: 10px;
                margin: 2% auto;
                display: block;
            }
            /*цифры*/
            .number{
                font-size: 4rem !important;
            }
            /*сетка бутстрап*/
            .col{
                padding-right: 1rem !important;
            }
            /*сетка бутстрап*/
            .col-4{
                max-width: 100%;
            }
            /*пункты списка*/
            li{
                margin-bottom: 1rem !important;
            }
            /*список*/
            ul{
                margin-left: -5% !important;
                margin-right: 5%;
            }
        }
        /*компонент - Этапы*/
        #Stages{
            /*сетка бутстрап*/
            .col-auto{
                width: 100% !important;
            }
            /*заголовки*/
            h3{
                font-size: 1.2rem;
                margin-bottom: 0.25rem;
            }
            h4{
                font-size: 1.15rem;
            }
            /*блок-карточка*/
            .card{
                padding: 0;
            }
            /*блок-таба-выбора, список*/
            .nav-item, .flex-column li{
                width: 42%;
                margin: 2% 4% 2% 4%;
                min-width: 42% !important;
            }
            /*блок-таба-выбора*/
            .nav-item .nav-link{
                padding: 0.5rem 0.1rem !important;
                min-height: 145px !important;
            }
            /*блок-таба-контент*/
            .tab-content{
                height: 250px;
                margin-left: 4%;
                margin-right: 3%;
            }
            /*блок-карточка (тело)*/
            .card-body{
                line-height: 1.2rem;
                padding: 0.8rem;
            }
            /*блок-карточка (текст, список)*/
            .card-text li{
                border: none;
                margin-top: 1% !important;
            }
        }
        /*компонент - Калькулятор*/
        #Calculation{
            /*контейнер, который включает в себя повтор блоков, кнопки*/
            .flex-container, button{
                width: 100%;
                margin-left: 0;
            }
            /*кнопки*/
            button{
                margin-top: 20px;
                padding: 10px 0;
            }
            /*контейнер, который включает в себя повтор блоков*/
            .flex-container{
                /*блоки*/
                div{
                    width: 50%;
                    padding: 5px 0;
                    /*блоки (второй,первый, шестой, седьмой, третий, восьмой)*/
                    &:nth-child(2),&:nth-child(1),&:nth-child(3),&:nth-child(6),&:nth-child(7),&:nth-child(8){
                        width: 50%;
                    }
                    /*блоки (второй)*/
                    &:nth-child(2){
                        border-top-right-radius: 10px;
                    }
                    /*блоки (пятый)*/
                    &:nth-child(5){
                        border-top-right-radius: 0;
                    }
                    /*блоки (шестой)*/
                    &:nth-child(6){
                        border-bottom-left-radius: 0;
                    }
                    /*блоки (девятый)*/
                    &:nth-child(9){
                        border-bottom-left-radius: 10px;
                    }
                    /*параграф*/
                    p{
                        margin-right: 0;
                        padding: 0.3rem;
                        font-size: .9rem
                    }
                }
            }
            /*форма*/
            .form-control{
                padding: .3rem;
                font-size: .9rem !important;
            }
            /*svg*/
            svg{
                height: 10px;
                padding: 0;
            }
        }
        /*компонент - Упаковка*/
        #Package{
            /*контейнер, который включает в себя повтор блоков*/
            .flex-container .row{
                width:100%;
                padding: 7.5px 15px 7.5px;
            }
            /*сетка бутстрап*/
            .col{
                padding-right: 0 !important;
            }
            /*сетка бутстрап*/
            .col-4{
                max-width: 20%;
            }
        }
        /*компонент - Футер*/
        #MyFooter{
            /*svg*/
            svg{
                width: 24px;
            }
            /*контейнер, который включает в себя повтор блоков*/
            .flex-container .inf{
                width: 45%;
                /*сетка бутстрап*/
                .row{
                    width: 100%;
                }
                /*последний блок*/
                &:last-child{
                    width: 55%;
                }
            }
        }
    }
    @media screen and (min-width: 300px) and (max-width: 500px){
        /*заголовки*/
        h1{
            font-size: 1.2rem !important;
            line-height: 2rem;
            margin: 25px 0 0 !important;
        }
        h2{
            font-size: 1.15rem !important;
            padding-bottom: 15px !important;
            padding-top: 0 !important;
            color: $colorImportant;
            text-decoration: none;
             &:before, &:after{
                display: none !important;
            }
        }
        /*компоненты - Виды, Этапы (заголовки)*/
        #Types h2, #Stages h2{
            text-decoration: none;
            text-underline-offset: 1px;
            text-decoration-color: $colorImportant;
        }
        /*компоненты - О нас, Калькулятор (заголовки)*/
        #About h2, #Calculation h2{
            font-size: 1.25rem !important;
        }
        /*форма, кнопки, списки (текст)*/
        .form-control, .btn, li{
            font-size: .9rem !important;
        }
        /*параграф*/
        p{
            font-size: .9rem;
        }
        /*компонент - Преимущества, О нас, Упаковка, Виды, Этапы, Калькулятор*/
        #Advantages, #About, #Package, #Types, #Stages, #Calculation{
            padding: 25px 0 35px;
        }
        /*компонент - Главная*/
        #Home{
            padding: 0 0 20px;
            /*список*/
            ul{
                margin: 20px 0 20px !important;
            }
            /*пункты списка*/
            li{
                margin: 10px 0 !important;
                font-size: 1rem !important;
                line-height: 1.3rem;
            }
            /*сетка бутстрап*/
            .row{
                flex-direction: column-reverse;
            }
            /*параграф*/
            p{
                margin-bottom: 6% !important;
            }
            /*параграф, кнопки*/
            p, button, .btn{
                font-size: .9rem !important;
            }
            /*кнопки*/
            button{
                padding: 8px 35px !important;
            }
            /*карусель*/
            .carousel{
                margin-left: 1%;
            }
            /*картинки в карусели*/
            .carousel img{
                width: 100%;
                height: 200px;
            }
            /*тень картинки (квадрат)*/
            .shadow{
                top: 7%;
                left: 13%;
                width: 83%;
                height: 97%;
                border: 3.5px solid $colorImportant;
            }
        }
        /*компонент - Преимущества*/
        #Advantages{
            /*сетка бутстрап*/
            .row{
                flex-direction: column;
                margin: 0;
                /*сетка бутстрап*/
                .row{
                    flex-direction: row;
                    margin: 0;
                }
            }
            /*цифры*/
            .number{
                font-size: 2.35rem;
                width: 60px;
                margin-bottom: 5%;
            }
            /*сетка бутстрап*/
            .col-2{
                max-width: 30%;
            }
            /*сетка бутстрап*/
            .col, .col-2{
                padding: 0 8px !important;
            }
            /*svg*/
            svg{
                width: 55px;
                padding: 0;
            }
            /*текст*/
            .text{
                height: 60px;
                margin-bottom: 0 !important;
            }
        }
        /*компоненты -  Виды*/
        #Types{
            /*сетка бутстрап*/
            .col-auto{
                width: 100% !important;
            }
            /*блок-контент*/
            .flex-column{
                flex-direction: row !important;
            }
            /*блок-таба-выбора, список*/
            .nav-item, .flex-column li{
                width: 100%;
                margin: 2% 2% 2% 2%;
                min-width: 45% !important;
            }
            /*заголовки*/
            h3{
                padding-bottom: 10px;
                font-size: 1.2rem;
            }
            /*блоки-табов-выбора*/
            .nav-pills .nav-link{
                min-height: 65px !important;
            }
            /*блок-карточка*/
            .card{
                padding: 0;
                margin-top: -4%;
            }
            /*блок-карточка-тело*/
            .card-body{
                padding: .8rem;
                height: 430px;
                line-height: 1.2rem;
            }
            /*блок-таба-контент*/
            .tab-content{
                margin-top: 10px;
                margin-right: 5px;
            }
        }
        /*компонент - О нас*/
        #About{
            с
            .row{
                flex-direction: column-reverse;
            }
            /*заголовки*/
            h2{
                padding-bottom: 10px;
            }
            /*блок под цифры*/
            .numbers {
                width: 210px;
                height: 210px;
                padding: 10px;
                margin: 2% auto;
                display: block;
            }
            /*цифры*/
            .number{
                font-size: 4rem !important;
            }
            /*сетка бутстрап*/
            .col{
                padding-right: 1rem !important;
            }
            /*сетка бутстрап*/
            .col-4{
                max-width: 100%;
            }
            /*пункты списка*/
            li{
                margin-bottom: 1rem !important;
            }
            /*список*/
            ul{
                margin-left: -5% !important;
                margin-right: 5%;
            }
        }
        /*компонент - Этапы*/
        #Stages{
            /*сетка бутстрап*/
            .col-auto{
                width: 100% !important;
            }
            /*заголовки*/
            h3{
                font-size: 1.15rem;
                margin-bottom: 0.25rem;
            }
            h4{
                font-size: 1.1rem;
            }
            /*блок-карточка*/
            .card{
                padding: 0;
            }
            /*блок-таба-выбора, список*/
            .nav-item, .flex-column li{
                width: 46%;
                margin: 2% 2% 2% 2%;
                min-width: 42% !important;
            }
            /*блок-таба-выбора*/
            .nav-item .nav-link{
                padding: 0.5rem 0.1rem !important;
                min-height: 130px !important;
            }
            /*блок-таба-контент*/
            .tab-content{
                height: 410px;
                margin-left: 4%;
                margin-right: 3%;
            }
            /*блок-карточка (тело)*/
            .card-body{
                line-height: 1.2rem;
                padding: 0.8rem;
            }
            /*блок-карточка (текст, список)*/
            .card-text li{
                border: none;
                margin-top: 1% !important;
            }
        }
        /*компонент - Калькулятор*/
        #Calculation{
            /*контейнер, который включает в себя повтор блоков, кнопки*/
            .flex-container, button{
                width: 100%;
                margin-left: 0;
            }
            /*кнопки*/
            button{
                margin-top: 20px;
                padding: 10px 0;
            }
            /*контейнер, который включает в себя повтор блоков*/
            .flex-container{
                /*блоки*/
                div{
                    width: 100%;
                    padding: 5px 0;
                    /*блоки (второй,первый, шестой, седьмой, третий, восьмой)*/
                    &:nth-child(2),&:nth-child(1),&:nth-child(3),&:nth-child(6),&:nth-child(7),&:nth-child(8){
                        width: 100%;
                    }
                    /*блоки (первый)*/
                    &:nth-child(1){
                        border-top-right-radius: 10px;
                    }
                    /*блоки (пятый)*/
                    &:nth-child(5){
                        border-top-right-radius: 0;
                    }
                    /*блоки (шестой)*/
                    &:nth-child(6){
                        border-bottom-left-radius: 0;
                    }
                    /*блоки (десятый)*/
                    &:nth-child(10){
                        border-bottom-left-radius: 10px;
                    }
                    /*параграф*/
                    p{
                        margin-right: 0;
                        padding: 0.3rem;
                        font-size: .9rem;
                    }
                }
            }
            /*форма*/
            .form-control{
                padding: .3rem;
                height: auto;
                font-size: .9rem !important;
                margin-bottom: 0 !important;
            }
            /*svg*/
            svg{
                width: 100px;
                height: 10px;
                padding: 0;
            }
        }
        /*компонент - Упаковка*/
        #Package{
            /*картинки*/
            img{
                width: 120%;
            }
            /*контейнер, который включает в себя повтор блоков*/
            .flex-container .row{
                width: 108%;
                padding: 7.5px 15px 7.5px;
            }
            /*сетка бутстрап*/
            .col-4{
                max-width: 28%;
            }
            /*сетка бутстрап*/
            .col{
                padding-right: 0 !important;
            }
        }
        /*компонент - Футер*/
        #MyFooter{
            /*svg*/
            svg{
                width: 20px;
            }
            /*контейнер, который включает в себя повтор блоков*/
            .flex-container .inf{
                width: 100%;
                /*сетка бутстрап*/
                .row{
                    margin-bottom: 4%;
                }
                /*перенос строки*/
                br{
                    display: none;
                }
                /*последний блок*/
                &:last-child{
                    /*параграф*/
                    p{
                        margin-bottom: 4% !important;
                    }
                }
            }
        }
    }
    @media screen and (max-width: 300px){
        /*svg логотипа*/
        .navbar-brand svg{
            width: 75%;
        }
        /*заголовки*/
        h1{
            font-size: 1.2rem !important;
            line-height: 2rem;
            margin: 25px 0 0 !important;
        }
        h2{
            font-size: 1.15rem !important;
            padding-bottom: 15px !important;
            padding-top: 0 !important;
            color: $colorImportant;
            text-decoration: none;
            &:before, &:after{
                display: none !important;
            }
        }
        /*компоненты - Виды, Этапы (заголовки)*/
        #Types h2, #Stages h2{
            text-decoration: none;
            text-underline-offset: 1px;
            text-decoration-color: $colorImportant;
        }
        /*компоненты - О нас, Калькулятор (заголовки)*/
        #About h2, #Calculation h2{
            font-size: 1.25rem !important;
        }
        /*форма, кнопки, списки (текст)*/
        .form-control, .btn, li{
            font-size: .85rem !important;
        }
        /*параграф*/
        p{
            font-size: .85rem;
        }
        /*компонент - Преимущества, О нас, Упаковка, Виды, Этапы, Калькулятор*/
        #Advantages, #About, #Package, #Types, #Stages, #Calculation{
            padding: 25px 0;
        }
        /*компонент - Главная*/
        #Home{
            padding: 0 0 20px;
            /*список*/
            ul{
                margin: 15px 0 15px !important;
            }
            /*пункты списка (сами пункты)*/
            ul > li:before{
                left: -30px;
            }
            /*пункты списка*/
            li{
                margin: 10px 0 !important;
                font-size: .9rem !important;
                line-height: 1.1rem;
            }
            /*сетка бутстрап*/
            .row{
                flex-direction: column-reverse;
            }
            /*параграф*/
            p{
                margin-bottom: 6% !important;
            }
            /*параграф, кнопки*/
            p, button, .btn{
                font-size: .9rem !important;
            }
            /*кнопки*/
            button{
                padding: 8px 35px !important;
            }
            /*карусель*/
            .carousel{
                margin-left: 1%;
            }
            /*картинки в карусели*/
            .carousel img{
                width: 100%;
                height: 150px;
            }
            /*тень картинки (квадрат)*/
            .shadow{
                top: 7%;
                left: 13%;
                width: 83%;
                height: 97%;
                border: 3px solid $colorImportant;
            }
        }
        /*компонент - Преимущества*/
        #Advantages{
            /*сетка бутстрап*/
            .row{
                flex-direction: column;
                margin: 0;
                /*сетка бутстрап*/
                .row{
                    flex-direction: row;
                    margin: 0;
                }
            }
            /*цифры*/
            .number{
                font-size: 2rem;
                width: 50px;
                margin-left: -5%;
                margin-bottom: 5%;
            }
            /*сетка бутстрап*/
            .col-2{
                max-width: 30%;
            }
            /*сетка бутстрап*/
            .col, .col-2{
                padding: 0 5px !important;
            }
            /*svg*/
            svg{
                width: 50px;
                margin-left: -5%;
                padding: 0;
            }
            /*текст*/
            .text{
                height: 60px;
                margin-bottom: 0 !important;
            }
        }
        /*компоненты -  Виды*/
        #Types{
            /*сетка бутстрап*/
            .col-auto{
                width: 100% !important;
            }
            /*блок-контент*/
            .flex-column{
                flex-direction: row !important;
            }
            /*блок-таба-выбора, список*/
            .nav-item, .flex-column li{
                width: 100%;
                margin: 2% 2% 2% 2%;
                min-width: 45% !important;
            }
            /*заголовки*/
            h3{
                padding-bottom: 10px;
                font-size: 1.15rem;
            }
            /*блоки-табов-выбора*/
            .nav-pills .nav-link{
                min-height: 65px !important;
            }
            /*блок-карточка*/
            .card{
                padding: 0;
                margin-top: -4%;
            }
            /*блок-карточка-тело*/
            .card-body{
                padding: .8rem;
                height: max-content;
                /*список*/
                ul{
                    margin-left: -8.5%;
                }
            }
            /*блок-таба-контент*/
            .tab-content{
                margin-top: 10px;
                width: 93%;
            }
        }
        /*компонент - О нас*/
        #About{
            /*компонент - О нас*/
            .row{
                flex-direction: column-reverse;
            }
            /*заголовки*/
            h2{
                padding-bottom: 10px;
            }
            /*блок под цифры*/
            .numbers{
                width: 180px;
                height: 180px;
                padding: 10px;
                margin: 2% auto;
                display: block;
                /*параграф*/
                p{
                    margin-bottom: 0 !important;
                }
            }
            /*цифры*/
            .number{
                font-size: 3.5rem !important;
                margin-bottom: 0 !important;
            }
            /*сетка бутстрап*/
            .col{
                padding-right: 1rem !important;
            }
            /*сетка бутстрап*/
            .col-4{
                max-width: 100%;
            }
            /*пункты списка*/
            li{
                margin-bottom: 1rem !important;
            }
            /*список*/
            ul{
                margin-left: -18% !important;
                margin-right: 5%;
            }
        }
        /*компонент - Этапы*/
        #Stages{
            /*сетка бутстрап*/
            .col-auto{
                width: 100% !important;
            }
            /*заголовки*/
            h3{
                font-size: 1.2rem;
                margin-bottom: 0.25rem;
            }
            h4{
                font-size: 1.1rem;
            }
            /*блок-карточка*/
            .card{
                padding: 0;
                /*список*/
                ol{
                    margin-left: -8.5%;
                }
            }
            /*блок-таба-выбора, список*/
            .nav-item, .flex-column li{
                width: 90%;
                margin: 2% 2% 2% 8%;
                min-width: 42% !important;
            }
            /*блок-таба-выбора*/
            .nav-item .nav-link{
                padding: 0.5rem 0.1rem !important;
                min-height: 130px !important;
            }
            /*блок-таба-контент*/
            .tab-content{
                height: max-content;
                margin-left: 4%;
                margin-right: 3%;
            }
            /*блок-карточка (тело)*/
            .card-body{
                line-height: 1.4rem;
                padding: 0.8rem;
            }
            /*блок-карточка (текст, список)*/
            .card-text li{
                border: none;
                margin-top: 1% !important;
            }
        }
        /*компонент - Калькулятор*/
        #Calculation{
            /*контейнер, который включает в себя повтор блоков, кнопки*/
            .flex-container, button{
                width: 100%;
                margin-left: 0;
            }
            /*кнопки*/
            button{
                margin-top: 20px;
                padding: 10px 0;
            }
            /*svg*/
            svg{
                display: none;
            }
            /*контейнер, который включает в себя повтор блоков*/
            .flex-container{
                /*блоки*/
                div{
                    width: 100%;
                    padding: 5px 0;
                    /*блоки (второй,первый, шестой, седьмой, третий, восьмой)*/
                    &:nth-child(2),&:nth-child(1),&:nth-child(3),&:nth-child(6),&:nth-child(7),&:nth-child(8){
                        width: 100%;
                    }
                    /*блоки (первый)*/
                    &:nth-child(1){
                        border-top-right-radius: 10px;
                    }
                    /*блоки (пятый)*/
                    &:nth-child(5){
                        border-top-right-radius: 0;
                    }
                    /*блоки (шестой)*/
                    &:nth-child(6){
                        border-bottom-left-radius: 0;
                    }
                    /*блоки (десятый)*/
                    &:nth-child(10){
                        border-bottom-left-radius: 10px;
                    }
                    /*параграф*/
                    p{
                        margin-right: 0;
                        padding: 0.3rem;
                        font-size: .9rem;
                    }
                }
            }
            /*форма*/
            .form-control{
                padding: .3rem;
                height: auto;
                font-size: .9rem !important;
                margin-bottom: 0 !important;
            }
            /*svg*/
            svg{
                width: 100px;
                height: 10px;
                padding: 0;
            }
        }
        /*компонент - Упаковка*/
        #Package{
            /*картинки*/
            img{
                width: 90%;
                margin-bottom: 4%;
            }
            /*контейнер, который включает в себя повтор блоков*/
            .flex-container .row{
                width: 110%;
                padding: 7.5px 15px 7.5px;
                flex-direction: column;
            }
            /*сетка бутстрап*/
            .col-4{
                max-width: 60%;
            }
            /*сетка бутстрап*/
            .col{
                padding-right: 0 !important;
            }
        }
        /*компонент - Футер*/
        #MyFooter{
            /*svg*/
            svg{
                width: 20px;
            }
            /*контейнер, который включает в себя повтор блоков*/
            .flex-container .inf{
                width: 100%;
                /*сетка бутстрап*/
                .row{
                    margin-bottom: 4%;
                }
                /*перенос строки*/
                br{
                    display: none;
                }
                /*последний блок*/
                &:last-child{
                    /*параграф*/
                    p{
                        margin-bottom: 4% !important;
                    }
                }
            }
        }
    }
</style>

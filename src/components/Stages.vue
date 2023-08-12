<template>
    <div id="Stages">
        <b-container>
            <h2>Процесс перевозок сборных грузов</h2>
            <b-card no-body>
                <b-tabs pills card vertical>
                    <b-tab v-for="(stages, index) in Stages" :title="stages.stage +'. '+stages.name ">
                        <b-card-text>
                            <h3>Этап {{stages.stage}}</h3>
                            <h4>{{stages.name}}</h4>
                            <ul>
                                <li v-for="(feature,index) in stages.list" :key="index">{{feature}}</li>
                            </ul>
                        </b-card-text>
                    </b-tab>
                </b-tabs>
            </b-card>
        </b-container>
    </div>
</template>

<script>
    export default {
        name: "Stages",
        data(){
            return{
                Stages:[
                    {
                        name:'Получение груза в Китае',
                        stage:'1',
                        list:[
                            'Заключение сделки и предоплата за товары',
                            'Поиск поставщика в Китае',
                            'Доставка груза с фабрики на пункт приема',
                            'Проверка количества товара',
                            'Подготовка груза к доставке в РФ'
                        ]
                    },
                    {
                        name:'Доставка груза в Россию',
                        stage:'2',
                        list:[
                            'Оформление экспорта в Россию',
                            'Страховка груза',
                            'Доставка груза из Китая на склад'
                        ]
                    },
                    {
                        name:'Таможенное оформление',
                        stage:'3',
                        list:[
                            'Сертификация',
                            'Декларирование',
                            'Обработка на складе временного хранения',
                            'Проверка комплекта сопроводительных документов'
                        ]
                    },
                    {
                        name:'Доставка до двери',
                        stage:'4',
                        list:[
                            'Оплата услуг компании',
                            'Доставка до пункта назначения по ж/д или автотранспортом',
                            'Выдача груза и документов'
                        ]
                    },
                ]
            }
        }
    }
</script>

<style>
   #Stages .nav-link{
       margin: -6% 6% 6% -8%;
   }
    #Stages .col-auto {
        width: 60% !important;
    }
    #Stages .flex-column {
        display: contents !important;
    }
    #Stages .flex-column li{
        width: 40%;
        float: left;
    }
    #Stages .nav-pills .nav-link {
        //min-height: 220px !important;
        display: flex;
        align-items: end;
        color: white;
    }
    #Stages .nav-pills .nav-link.active{
        color: #8e4404 !important;
        filter: contrast(90%) brightness(190%);
        font-weight: 600 !important;
    }
    .card-header {
        padding: 0 !important;
    }
    .card{
        padding: 0 3.25rem;
        background: transparent !important;
    }
    #Stages .tab-content{
        background-size: 100% 100% !important;
        background: #1C1D1E;
        margin-left: 10px;
        margin-top: 1%;
        height: 500px;
        border: 2px solid rgba(255, 122, 0, 0.37);
        border-radius: 10px;
    }
    #Stages p{
        font-size: 1.25rem;
    }
    #Stages li{
        min-width: 40%;
        margin: 4%;
        border: 2px solid #FF7A00;
        border-radius: 5px;
        font-family: "Montserrat", sans-serif;
        font-size: 1.25rem;
        font-weight: 400 !important;
        margin-bottom: 0.5rem !important;
    }
    #Stages .card-text li{
        border: none;
        margin-top: 4% !important;
    }
    #Stages .card-text h4{
        text-align: center;
        font-weight: 700 !important;
        margin-top: -3%;
        margin-bottom: 5% !important;
    }

    #Stages li:nth-child(1) .nav-link{
        background-size: 100% 100% !important;
        background: url("../../public/stages/11.png");
        min-height: 220px !important;
    }
    #Stages li:nth-child(2) .nav-link{
        background-size: 100% 100% !important;
        background: url("../../public/stages/22.png");
        min-height: 220px !important;
    }
    #Stages li:nth-child(3) .nav-link{
        background-size: 100% 100% !important;
        background: url("../../public/stages/33.png");
        min-height: 220px !important;
    }
    #Stages li:nth-child(4) .nav-link{
        background-size: 100% 100% !important;
        background: url("../../public/stages/44.png");
        min-height: 220px !important;
    }
    #Stages li:nth-child(4){
        margin-bottom: 0 !important;
    }
</style>
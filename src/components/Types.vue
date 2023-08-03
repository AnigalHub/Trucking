<template>
    <div id="Types">
        <b-container>
            <h2>Виды грузоперевозок</h2>
            <b-card no-body>
                <b-tabs pills card vertical>
                    <b-tab v-for="(types, index) in Types" :title="types.name">
                        <b-card-text>
                            <h3>{{types.name}}</h3>
                            <p>{{types.text}}</p>
                            <p>Преимущества:</p>
                            <ul>
                                <li v-for="(feature,index) in types.list" :key="index">{{feature}}</li>
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
        name: "Types",
        data(){
            return{
                Types:[
                    {
                        name:'Авиаперевозки',
                        text:'Используется при доставке дорогих или скоропортящихся товаров.',
                        list:[
                            'Самое быстрое время доставки. Расстояние между странами преодолевается за часы',
                            'Минимальный риск порчи, повреждений и полной утраты груза',
                            'Возможность отправки товаров с любыми характеристиками. Размеры лайнера вмещают разные объекты'
                        ]
                    },
                    {
                        name:'Автоперевозки',
                        text:'Автомобильные перевозки позволяют привезти как скоропортящиеся продукты, так и практически все виды оборудования.',
                        list:[
                            'Высока скорость доставки',
                            'Оптимальный выбор маршрута. Автомобильные дороги проложены во всех уголах стран',
                            'Выбор соответствующего авто под конкретный груз (учитывая габариты и веса груза)',
                            'Возможные отклонения от сроков минимальны'
                        ]
                    },
                    {
                        name:'Железнодорожные перевозки',
                        text:'В основном железнодорожные перевозки используются для поставки крупногабаритных грузов или больших партий.',
                        list:[
                            'Всепогодность. Неблагоприятных погодных условий при такой грузоперевозки не существует',
                            'Развитая железнодорожная сеть России и Китая',
                            'Грузоподъемность. В одном вагоне возможно перевозить 60 тонн груза'
                        ]
                    },
                    {
                        name:'Морские перевозки',
                        text:'Используется для больших партий товаров и габаритных грузов.',
                        list:[
                            'Самая низкая стоимость среди всех грузоперевозок',
                            'Простая логистика',
                            'Минимизация рисков внешнего воздействия на груз'
                        ]
                    },
                ]
            }
        }
    }
</script>

<style>
    .nav-pills .nav-link {
        min-height: 120px !important;
        display: flex;
        justify-content: center;
        align-items: center;
        color: white;
    }
    .nav-pills .nav-link.active{
        color: #FF7A00 !important;
        filter: contrast(90%) brightness(150%);
    }
    .card-header {
        padding: 0 !important;
    }
    .card{
        padding: 0 3.25rem;
        background: transparent !important;
    }
    #Types .tab-content{
        background-size: 100% 100% !important;
        background: url("../../public/types/55.jpg");
        margin-left: 10px;
        border: 2px solid #FF7A00;
        border-radius: 5px;
    }
    #Types p{
        font-size: 1.25rem;
    }
    #Types li{
        margin: 0 0 5px;
        border: 2px solid #FF7A00;
        border-radius: 5px;
        font-family: "Montserrat", sans-serif;
        font-size: 1.25rem;
        font-weight: 400 !important;
        margin-bottom: 0.5rem !important;
    }
    #Types .card-text li{
        border: none;
        margin-top: 3% !important;
    }
    #Types li:nth-child(1) .nav-link{
        background-size: 100% 100% !important;
       background: url("../../public/types/11.jpg");
    }
    #Types li:nth-child(2) .nav-link{
        background-size: 100% 100% !important;
        background: url("../../public/types/22.jpg");
    }
    #Types li:nth-child(3) .nav-link{
        background-size: 100% 100% !important;
        background: url("../../public/types/33.jpg");
    }
    #Types li:nth-child(4) .nav-link{
        background-size: 100% 100% !important;
        background: url("../../public/types/44.jpg");
    }
    #Types li:nth-child(4){
        margin-bottom: 0 !important;
    }
</style>
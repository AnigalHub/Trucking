<template>
    <div id="Stages">
        <b-container>
            <h2>Процесс перевозок сборных грузов</h2>
            <b-card no-body>
                <b-tabs pills card vertical>
                    <b-tab v-for="(stages, index) in Stages" :title="stages.stage +'. '+ stages.name ">
                        <b-card-text>
                            <h3>Этап {{stages.stage}}</h3>
                            <h4>{{stages.name}}</h4>
                            <ol>
                                <li v-for="(feature,index) in stages.list" :key="index">{{feature}}</li>
                            </ol>
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
                            'Оформление сопроводительных документов по экспорту в Россию',
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
                        name:'Доставка до двери заказчика',
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

<style scoped>

</style>
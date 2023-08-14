<template>
    <div id="Package">
        <b-container>
            <h2><span>Упаковка груза</span></h2>
            <p>Мы отвечаем за ваш груз и максимально защищаем его от царапин и любых других механических повреждений. На наших складах созданы все условия, чтобы правильно и быстро упаковать любой груз.</p>
            <p>Подбор, расчет стоимости и изготовление упаковки происходит индивидуально под каждый груз с учетом его параметров и особенностей транспортного средства.</p>
            <p>Наша компания использует следующие виды упаковки груза:</p>
            <div class="flex-container">
                <b-row v-for="packages in Package" :key="packages.index">
                    <b-col cols="4">
                        <img :src="packages.src" :alt="packages.alt">
                    </b-col>
                    <b-col>
                        <p class="name">{{packages.name}}</p>
                        <p class="text">{{packages.text}}</p>
                    </b-col>
                </b-row>
            </div>
        </b-container>
    </div>
</template>

<script>
    export default {
        name: "Package",
        data(){
            return{
                Package: [
                    {
                        src:'./package/1.png',
                        alt:'1',
                        name:'Деревянная обрешотка',
                        text:'Защита от механических повреждений и различных косаний'
                    },
                    {
                        src:'./package/2.png',
                        alt:'2',
                        name:'Стрейч-плёнка',
                        text:'Скрепление груза,  состоящего из нескольких элементов'
                    },
                    {
                        src:'./package/3.png',
                        alt:'3',
                        name:'Пузырчатая полиэтиленовая пленка',
                        text:'Защита от ударов, мелких царапин и потертостей'
                    },
                    {
                        src:'./package/4.png',
                        alt:'4',
                        name:'Полипропиленовый мешок',
                        text:'Защита от пыли и нарушения целостности груза'
                    },
                ],
            }
        }
    }
</script>

<style scoped lang="scss">
    .flex-container {
        .row{
            width: 49%;
            padding: 15px;
        }
        .name{
            text-decoration: underline;
            text-underline-offset: 10px;
            text-decoration-color: #FF7A00;
        }
    }
</style>
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
                        src:'./package/woodenbox.png',
                        alt:'деревянная обрешотка',
                        name:'Деревянная обрешотка',
                        text:'Защита от механических повреждений и различных косаний'
                    },
                    {
                        src:'./package/stretchfilm.png',
                        alt:'стрейч плёнка',
                        name:'Стрейч-плёнка',
                        text:'Скрепление груза,  состоящего из нескольких элементов'
                    },
                    {
                        src:'./package/bubblewrap.png',
                        alt:'пузырчатая полиэтиленовая пленка',
                        name:'Пузырчатая полиэтиленовая пленка',
                        text:'Защита от ударов, мелких царапин и потертостей'
                    },
                    {
                        src:'./package/polypropylenebag.png',
                        alt:'полипропиленовый мешок',
                        name:'Полипропиленовый мешок',
                        text:'Защита от пыли и нарушения целостности груза'
                    },
                ],
            }
        }
    }
</script>

<style scoped>

</style>
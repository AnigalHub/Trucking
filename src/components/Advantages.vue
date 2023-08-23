<template>
    <div id="Advantages">
        <b-container>
            <h2><span>Преимущества</span></h2>
            <b-row>
                <b-col>
                    <b-row v-for="advantages in Advantages1" :key="advantages.index">
                        <b-col cols="2">
                            <div class="number">{{advantages.number}}</div>
                            <p class="descr">{{advantages.descr}}</p>
                        </b-col>
                        <b-col>
                            <p class="text">{{advantages.text}}</p>
                        </b-col>
                    </b-row>
                </b-col>
                <b-col>
                    <b-row v-for="advantages in Advantages2" :key="advantages.index">
                        <b-col cols="2">
                            <component :is="advantages.number"/>
                        </b-col>
                        <b-col>
                            <p class="text">{{advantages.text}}</p>
                        </b-col>
                    </b-row>
                </b-col>
            </b-row>
        </b-container>
    </div>
</template>

<script>
    import insurance from './svg/advantages/insurance';
    import delivery from './svg/advantages/delivery';
    import customs from './svg/advantages/customs';
    export default {
        name: "Advantages",
        data(){
            return{
                Advantages1: [
                    {
                        number:'30',
                        descr:'кг',
                        text:'Минимальный вес партии для отправки'
                    },
                    {
                        number:'5-7',
                        descr:'дней',
                        text:'Средние сроки доставки'
                    },
                    {
                        number:'3$',
                        descr:'за кг',
                        text:'Минимальная стоимость'
                    }
                ],
                Advantages2: [
                    {
                        number:customs,
                        text:'Таможенное оформление грузов день в день'
                    },
                    {
                        number:insurance,
                        text:'Страховка грузов'
                    },
                    {
                        number:delivery,
                        text:'Возможность доставки до двери'
                    }
                ],
            }
        }
    }
</script>

<style scoped>

</style>
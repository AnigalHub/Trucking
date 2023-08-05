<template>
    <div id="Advantages">
        <b-container>
            <div class="title">
                <span>
                    <h2>Преимущества</h2>
                </span>
            </div>
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
        height: 110px;
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
</style>
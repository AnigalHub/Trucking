<template>
    <div id="Home">
        <b-container>
            <b-row>
                <b-col>
                    <h1>Перевозка грузов из Китая:</h1>
                    <ul>
                        <li>Подбор товара c учетом требований заказчика</li>
                        <li>Поиск надежного поставщика</li>
                        <li>Доставка сборных грузов любой категории</li>
                    </ul>
                    <b-button><a href="#Calculation">Оставить заявку</a></b-button>
                </b-col>
                <b-col>
                    <b-carousel id="carousel-fade" fade indicators>
                        <b-carousel-slide v-for="images in Images">
                            <template v-slot:img>
                                <img :src="images.src" :alt="images.alt"/>
                            </template>
                        </b-carousel-slide>
                    </b-carousel>
                    <div class="shadow"></div>
                </b-col>
            </b-row>
        </b-container>
    </div>
</template>

<script>
    export default {
        name: "Home",
        data(){
            return{
                Images:[
                    {
                        src:'./home/storage.png',
                        alt:'склад'
                    },
                    {
                        src:'./home/trucking.png',
                        alt:'автоперевозки'
                    },
                    {
                        src:'./home/cargo.png',
                        alt:'груз'
                    },
                    {
                        src:'./home/airtransportation.png',
                        alt:'авиаперевозки'
                    },
                ]
            }
        }
    }
</script>

<style scoped>

</style>
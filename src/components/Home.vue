<template>
    <div id="Home">
        <b-container>
            <b-row>
                <b-col>
                    <h1>Доставка сборных грузов из Китая </h1>
                    <p>Надежная перевозка груза любой категории</p>
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
                        src:'./home/1.png',
                        alt:'1'
                    },
                    {
                        src:'./home/2.png',
                        alt:'2'
                    },
                    {
                        src:'./home/3.png',
                        alt:'3'
                    },
                    {
                        src:'./home/4.png',
                        alt:'4'
                    },
                ]
            }
        }
    }
</script>

<style scoped>

</style>
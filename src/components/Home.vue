<template>
    <div id="Home">
        <b-container>
            <b-row>
                <b-col>
                    <h1>Доставка сборных грузов из Китая </h1>
                    <p>Надежная перевозка груза любой категории</p>
                    <b-button>Оставить заявку</b-button>
                </b-col>
                <b-col>
                    <b-carousel
                            id="carousel-fade" fade indicators>
                        <b-carousel-slide>
                            <template v-slot:img>
                                <img src="../../public/home/1.png" alt="двойная_накладка"/>
                            </template>
                        </b-carousel-slide>
                        <b-carousel-slide>
                            <template v-slot:img>
                                <img src="../../public/home/2.png" alt="накладка_на_выключатель"/>
                            </template>
                        </b-carousel-slide>
                        <b-carousel-slide>
                            <template v-slot:img>
                                <img src="../../public/home/3.png" alt="накладка_на_розетку"/>
                            </template>
                        </b-carousel-slide>
                        <b-carousel-slide>
                            <template v-slot:img>
                                <img src="../../public/home/4.png" alt="тройная_накладка"/>
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
    }
</script>

<style scoped lang="scss">
img{
    width: 100%;
    height: 400px;
}

</style>
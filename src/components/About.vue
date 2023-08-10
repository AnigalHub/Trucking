<template>
    <div id="About">
        <b-container>
            <b-row>
                <b-col cols="4">
                    <b-carousel id="carousel-fade" fade indicators>
                        <b-carousel-slide v-for="images in Circle">
                            <template v-slot:img>
                                <div class="numbers">
                                    <p>более</p>
                                    <p class="number">{{images.number}}</p>
                                    <p>{{images.text}}</p>
                                </div>
                            </template>
                        </b-carousel-slide>
                    </b-carousel>
                </b-col>
                <b-col>
                    <h2>О нас</h2>
                    <ul>
                        <li v-for="(list,index) in List" :key="index">{{list}}</li>
                    </ul>
                </b-col>
            </b-row>
        </b-container>
    </div>
</template>

<script>
    export default {
        name: "About",
        data(){
            return{
                List:[
                    'Быстрая и качественная перевозка',
                    'Сохранность груза',
                    'Гибкость и оперативность во внештаных ситуациях',
                    'Достижение целей через совместные усилия стран',
                    'Доступные цены'
                ],
                Circle:[
                    {
                        number:'15',
                        text:'лет успешной работы'
                    },
                    {
                        number:'5',
                        text:'тыс. довольных клиентов'
                    },
                    {
                        number:'100',
                        text:'тыс. доставленных грузов',
                    }
                ]
            }
        }
    }
</script>

<style scoped>
    li{
        list-style-type:none;
        border-bottom: 2px solid #FF7A00;
        font-family: "Montserrat", sans-serif;
        font-size: 1.25rem;
        font-weight: 400 !important;
        margin-bottom: 1.5rem !important;
    }
    p{
        text-align: center;
    }
    .number{
        color: #FF7A00;
        font-size: 6rem;
        text-align: center;
        transform: scale(1.2, 1.2);
    }
    .numbers{
        border-radius: 50%;
        width: 300px;
        height: 300px;
        padding: 20px 20px 0;
        margin: 28% auto 0 10%;
        border: 2px solid #FF7A00;
    }

</style>
<style>
    .carousel-indicators{
        display: none !important;
    }
</style>
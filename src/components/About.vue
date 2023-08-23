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

</style>
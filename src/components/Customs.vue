<template>
    <div id="Customs">
        <b-container>
            <div class="title">
                <h2><span>Официальный таможенный представитель</span></h2>
            </div>
            <div class="flex-container">
                <div v-for="value in Customs" :key="value.index">
                    <img :src="value.src" :alt="value.alt" @click="showModal(value)">
                </div>
            </div>
            <b-carousel id="carousel-fade" fade indicators>
                <b-carousel-slide v-for="value in Customs">
                    <template v-slot:img>
                        <img :src="value.src" :alt="value.alt" @click="showModal(value)"/>
                    </template>
                </b-carousel-slide>
            </b-carousel>
            <b-modal ref="my-modal" id="img" size="lg" centered :title="selectedImages.name">
                <img :src="selectedImages.src" :alt="selectedImages.alt"/>
            </b-modal>
            <p>Мы работаем честно и прозрачно: каждый шаг подтверждается документами, каждое действие соответствует законам КНР или РФ</p>
        </b-container>
    </div>
</template>

<script>
    import increase from './svg/increase';
    export default {
        name: "Customs",
        data(){
            return{
                svg:increase,
                selectedImages:{
                    src:'',
                    alt:'',
                },
                Customs: [
                    {
                        src:'./customs/license1.png',
                        alt:'лицензия1'
                    },
                    {
                        src:'./customs/license2.png',
                        alt:'лицензия2'
                    },
                    {
                        src:'./customs/license3.png',
                        alt:'лицензия3'
                    }
                ],
            }
        },
        methods: {
            showModal(img) {
                this.selectedImages = img;
                this.$refs['my-modal'].show()
            },
        }
    }
</script>

<style scoped>

</style>
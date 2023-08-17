<template>
    <div id="Customs">
        <b-container>
            <div class="title">
                <h2><span>Официальный таможенный представитель</span></h2>
            </div>
            <b-row>
                <b-col v-for="value in Customs" :key="value.index">
                    <img :src="value.src" :alt="value.alt">
                    <component :is="svg"/>
                </b-col>
            </b-row>
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
                Customs: [
                    {
                        src:'./customs/1.png',
                        alt:''
                    },
                    {
                        src:'./customs/2.png',
                        alt:''
                    },
                    {
                        src:'./customs/3.png',
                        alt:''
                    }
                ],
            }
        }
    }
</script>

<style scoped>
    img{
        width: 100%;
        filter: brightness(50%);
    }
    p{
        margin-top: 3%;
    }
    svg{
        width: 60px;
        margin: 0 auto;
        display: block;
        position: absolute;
        top: 40%;
        left: 42%;
    }
</style>
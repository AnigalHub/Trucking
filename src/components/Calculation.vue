<template>
    <div id="Calculation">
        <b-container>
            <h2>Расчет стоимости доставки груза</h2>
            <div class="flex-container">
                <div>
                    <b-form-input autocomplete="off" type="text" placeholder="Пункт отправления"/>
                </div>
                <div>
                    <b-form-input autocomplete="off" type="text" placeholder="Наименование товара"/>
                </div>
                <div>
                    <b-form-input autocomplete="off" type="text" placeholder="ФИО"/>
                </div>
                <div>
                    <b-form-input autocomplete="off" type="text" placeholder="Вес груза, кг"/>
                </div>
                <div>
                    <p>Страховка</p>
                    <label class="switch">
                        <input type="checkbox">
                        <span class="slider round"></span>
                    </label>
                </div>
                <div>
                    <b-form-input autocomplete="off" type="text" placeholder="Пункт назначения"/>
                </div>
                <div>
                    <b-form-input autocomplete="off" type="text" placeholder="+7(9**)***-**-**"/>
                </div>
                <div>
                    <b-form-input autocomplete="off" type="text" placeholder="Email"/>
                </div>
                <div>
                    <b-form-input autocomplete="off" type="text" placeholder="Объем груза, м3"/>
                </div>
                <div>
                    <p>Упаковка</p>
                    <label class="switch">
                        <input type="checkbox">
                        <span class="slider round"></span>
                    </label>
                </div>
            </div>
            <b-button>ОТПРАВИТЬ ЗАЯВКУ  <component :is="svg"/></b-button>
        </b-container>
    </div>
</template>

<script>
    import arrow from './svg/arrow';
    export default {
        name: "Calculation",
        data(){
            return{
                svg:arrow,
            }
        }
    }
</script>

<style scoped lang="scss">
    .flex-container {
        width: 105%;
        margin-left: -2.5%;
        div{
            border: .25px solid rgba(255, 122, 0, 0.45);
            background: #1F1E1E;
            width: 20%;
            padding: 15px 0;
            &:first-child{
                border-top-left-radius: 20px 20px;
            }
            &:nth-child(5){
                border-top-right-radius: 20px 20px;
            }
            &:nth-child(6){
                border-bottom-left-radius: 20px 20px;
            }
            &:last-child{
                border-bottom-right-radius: 20px 20px;
            }
            p{
                float: left;
                font-size: 1.1rem;
                margin-right: 10px;
                padding: 0.375rem 15px;
            }
        }
    }
    button{
        margin-top: 30px;
        border-radius: 10px;
        width: 105%;
        margin-left: -2.5%;
        background: rgba(255, 122, 0, 0.2);
        padding: 15px 0;
        border: .25px solid rgba(255, 122, 0, 0.45);
    }
    .form-control {
        background: transparent;
        border: none;
    }
    svg{
        padding-left: 15px;
    }
</style>
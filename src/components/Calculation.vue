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
                    <b-form-input autocomplete="off" type="number" placeholder="Объем груза, м3"/>
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

<style scoped>

</style>
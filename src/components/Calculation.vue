<template>
    <div id="Calculation">
        <b-container>
            <h2>Расчет стоимости доставки груза</h2>
            <form class="flex-container">
                <div><b-form-input autocomplete="off" v-model="formCalculation.departure" type="text" placeholder="Пункт отправления"/></div>
                <div><b-form-input autocomplete="off" v-model="formCalculation.arrival" type="text" placeholder="Пункт назначения"/></div>
                <div><b-form-input autocomplete="off" v-model="formCalculation.name" type="text" placeholder="Наименование"/></div>
                <div><b-form-input autocomplete="off" v-model="formCalculation.fio" type="text" placeholder="ФИО"/></div>
                <div><b-form-input autocomplete="off" v-model="formCalculation.phone" type="tel" v-mask="'+7 (###) ###-##-##'" placeholder="+7(9**)***-**-**"/></div>
                <div><b-form-input autocomplete="off" v-model="formCalculation.email" type="text" placeholder="Email"/></div>
                <div><b-form-input autocomplete="off" v-model="formCalculation.volume" type="number" placeholder="Объем груза, м3"/></div>
                <div><b-form-input autocomplete="off" v-model="formCalculation.weight" type="text" placeholder="Вес груза, кг"/></div>
                <div><b-form-checkbox v-model="formCalculation.insurance" name="check-button" switch><p>Страховка</p></b-form-checkbox></div>
                <div><b-form-checkbox v-model="formCalculation.package" name="check-button" switch><p>Упаковка</p></b-form-checkbox></div>
            </form>
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
                formCalculation:{
                    departure:'',
                    arrival:'',
                    name: '',
                    fio:'',
                    phone: '',
                    email:'',
                    volume:'',
                    weight:'',
                    insurance: false,
                    package: false,
                },
            }
        }
    }
</script>

<style scoped>

</style>
<template xmlns="">
    <b-navbar id="Nav" class="navbar-expand-xl sticky-top" toggleable>
        <b-container>
            <b-navbar-brand href="#Home">
                <component :is="svg"/>
            </b-navbar-brand>
            <b-navbar-toggle target="navbar-toggle-collapse">
                <template v-slot:default="{ expanded }">
                    <b-icon v-if="expanded" icon="chevron-bar-up"></b-icon>
                    <b-icon v-else icon="chevron-bar-down"></b-icon>
                </template>
            </b-navbar-toggle>
            <b-collapse id="navbar-toggle-collapse" class="justify-content-lg-start" is-nav>
                <b-navbar-nav>
                    <b-nav-item href="#About">О нас</b-nav-item>
                    <b-nav-item href="#Advantages">Преимущества</b-nav-item>
                    <b-nav-item href="#Stages">Этапы работы</b-nav-item>
                    <b-nav-item href="#Types">Грузоперевозки</b-nav-item>
                    <b-nav-item href="#Calculation">Расчет стоимости</b-nav-item>
                    <b-nav-item href="#Package">Упаковка</b-nav-item>
                    <b-nav-item href="#MyFooter">
                        <a :href="href" :target="target">
                            {{http}}
                        </a>
                    </b-nav-item>
                </b-navbar-nav>
            </b-collapse>
        </b-container>
    </b-navbar>
</template>

<script>
    import logo from './svg/logo';
    import information from '../../public/documents/information.json';
    export default {
        name: "navbar",
        data(){
            return{
                svg:logo,
                href:'tel:' + information.telephone,
                target:'_self',
                http:information.telephone
            }
        }
    }
</script>

<style scoped lang="scss">
    /*название компании*/
    .name_company{
        font-size: 1.3rem ;
    }
    /*текст при раскрытом меню в мобильном варианте*/
    .navbar-light .navbar-toggler {
        color: #ffffff;
    }
    /*блок под логотип(картинка, название компании, что за компания(производственная))*/
    .navbar-brand{
        padding-top: 0 !important;
        padding-bottom: 0 !important;
        svg{
            width: 100%;
            transform: scale(1.1, 1);
            height: 45px;
        }
    }
    /*меню на всех экранах (которое будет и складываться на маленьких экранах и раскрываться на больших)*/
    .navbar{
        background:#010101;
        background-size:cover;
        padding: 5px 0
    }
    /*все кнопки в меню*/
    .nav-link{
        color: #ffffff !important;
        padding-right: .7rem !important;
        padding-left: .7rem !important;
        font-family: "Montserrat", sans-serif;
        font-size: 1rem;
        font-weight: 400 !important;
        a{
            color: #FF7A00 !important;
        }
    }
    /*АДАПТИВНОСТЬ*/
    @media screen and (max-width: 768px) {
        /*все кнопки в меню*/
        .nav-link {
            font-size: .9rem;
            padding: 0.2rem 0 !important;
        }
    }
    @media screen and (max-width: 1200px) {
        /*меню на всех экранах (которое будет и складываться на маленьких экранах и раскрываться на больших)*/
        .navbar{
            background:rgb(10 15 24 / 98%);
        }
    }
</style>
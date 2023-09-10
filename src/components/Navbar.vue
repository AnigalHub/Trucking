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
            <b-collapse id="navbar-toggle-collapse" class="justify-content-end" is-nav v-model="isExpanded">
                <b-navbar-nav>
                    <b-nav-item  @click="scrollToId" href="#About">О нас</b-nav-item>
                    <b-nav-item  @click="scrollToId" href="#Advantages">Преимущества</b-nav-item>
                    <b-nav-item  @click="scrollToId" href="#Stages">Этапы работы</b-nav-item>
                    <b-nav-item  @click="scrollToId" href="#Types">Грузоперевозки</b-nav-item>
                    <b-nav-item  @click="scrollToId" href="#Calculation">Расчет стоимости</b-nav-item>
                    <b-nav-item  @click="scrollToId" href="#Package">Упаковка</b-nav-item>
                    <b-nav-item  @click="scrollToId" href="#MyFooter">
                        <a :href="'tel:'+ information.telephone" target="_self">{{information.telephone}}</a>
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
                information: information,
                isExpanded: false,
            }
        },
        methods:{
            scrollToId(event){
                let offsetY = 70;
                if(this.isExpanded){
                    let nav = document.getElementById(("Nav"));
                    let bounds =  nav.getBoundingClientRect();
                    offsetY = bounds.height;
                }
                let element = document.getElementById(event.target.hash.replace("#", ""));
                window.scrollTo({top: element.offsetTop - offsetY, left: 0, behavior: 'smooth'});
                event.preventDefault();
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
            width: 150px;
            transform: scale(1.1, 1);
            height: 45px;
        }
    }
    /*меню на всех экранах (которое будет и складываться на маленьких экранах и раскрываться на больших)*/
    .navbar{
        background: #010101;
        background-size:cover;
        padding: 5px 0
    }
    /*все кнопки в меню*/
    .nav-link{
        color: #ffffff !important;
        padding-right: .65rem !important;
        padding-left: .65rem !important;
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
</style>
<template>
    <div id="MyFooter">
        <b-container>
            <div class="flex-container">
                <div class="inf">
                    <b-row>
                        <b-col cols="1"><component :is="telephone"/></b-col>
                        <b-col>
                            <p><a :href="'tel:'+ information.telephone" target="_self">{{information.telephone}}</a></p>
                        </b-col>
                    </b-row>
                </div>
                <div class="inf">
                    <b-row>
                        <b-col cols="1"><component :is="document"/></b-col>
                        <b-col><p><a :href="'mailto:'+ information.mail" target="_self">{{information.mail}}</a></p></b-col>
                    </b-row>
                </div>
            </div>
        </b-container>
    </div>
</template>

<script>
    import information from '../../public/documents/information.json';
    import telephone from './svg/myfooter/telephone';
    import document from './svg/myfooter/document';
    export default {
        name: "MyFooter",
        data(){
            return{
                information: information,
                telephone: telephone,
                document:document
            }
        }
    }
</script>

<style scoped>

</style>

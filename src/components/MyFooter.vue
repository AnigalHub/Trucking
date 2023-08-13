<template>
    <div id="MyFooter">
        <b-container>
            <b-row>
                <b-col>
                    <b-row>
                        <b-col cols="1"><component :is="telephone"/></b-col>
                        <b-col><p>{{information.telephone}}</p></b-col>
                    </b-row>
                    <br/>
                    <b-row>
                        <b-col cols="1"><component :is="document"/></b-col>
                        <b-col><p>{{information.mail}}</p></b-col>
                    </b-row>
                </b-col>
                <b-col>
                    <p>{{information.city}}</p>
                    <br/>
                    <p>{{information.address}}</p>
                </b-col>
            </b-row>
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
svg{
    width: 30px;
}
</style>
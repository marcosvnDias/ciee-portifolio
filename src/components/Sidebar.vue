<script>
    import MeetingPage from "./MeetingPage.vue"
    import { dateMeetings } from "../dates/dateMeetings"

    export default {
        name: "Sidebar",
        components: { MeetingPage },
        data() {
            return {
                arrayEncontros: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10],
                contentMeeting: {},
                focusPage: false,
                openPage: false,
                meetings: dateMeetings,
            }
        },
        methods: {
            openContent(element){
                this.openPage = false;
                setTimeout(() => this.openPage = true, 100)
                // this.openPage = true;
                this.contentMeeting = this.meetings[element - 1]
            }
        }
    }
</script>

<template>
    <div class="box-sidebar">
        <ul class="itens-sidebar">
            <li v-for="encontro in arrayEncontros" @click="openContent(encontro)">
                <div class="body-spear"></div>

                <div class="spear-header">
                    <p>{{ encontro }}</p>
                </div>
            </li>
        </ul>


        <div class="content-meeting" v-if="openPage">
            <p>
               {{ contentMeeting.numberMeeting + "º Encontro)"}}  {{ contentMeeting.text[0] }}<br><br>

                {{ contentMeeting.text[1] }}<br  v-if="contentMeeting.text.length >= 3"><br v-if="contentMeeting.text.length >= 3">

                {{ contentMeeting.text[2] }}<br v-if="contentMeeting.text.length >= 4"><br v-if="contentMeeting.text.length >= 3">

                {{ contentMeeting.text[3] }}
            </p>
        </div>
    </div>
</template>

<style scoped>
    .box-sidebar{
        min-height: 100vh;
        display: flex;
        align-items: center;
        justify-content: space-between;
        position: relative;
        padding: 0px 20px;
    }

    .itens-sidebar{
        min-height: 100vh;
        display: flex;
        flex-direction: column;
        justify-content: center;
        /* justify-content: space-around; */
        gap: 10px;
    }

    .body-spear{
        height: 45px;
        width: 0px;
        transition: 0.3s;
    }

    .spear-header{    
        height: 45px;
        width: 100px;
        display: flex;
        align-items: center;
        justify-content: center;
        background-color: rgb(236, 236, 236);
        /* border-radius: 0px 100% 100% 0px; */
        box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.753);
        cursor: pointer;
        position: relative;
        transition: 0.3s;
    }

    .spear-header::after{
        content: "";
        height: 32px;
        width: 32px;
        background-color: rgb(236, 236, 236);
        right: -16px;
        position: absolute;
        transform: rotate(45deg);
        z-index: 1;
    }

    li{
        display: flex;
        list-style: none;
    }

    li:hover .body-spear{
        width: 20px;
        background-color: rgb(107, 30, 30);
        transition: 0.3s;
    }

    .focus{
        width: 20px;
        background-color: rgb(107, 30, 30);
        transition: 0.3s;
    }

    .content-meeting{
        width: 50%;
        background-color: white;
        border-radius: 8px;
        position: absolute;
        left: 300px;
        padding: 12px 20px;
        box-shadow: 0px 0px 20px rgb(0 0 0 / 69%);
        animation: 0.8s fadin;
    }

    p{
        font-size: 14px;
    }

    @media screen and (max-width: 720px) {
        /* .spear-header{    
            height: 25px;
            width: 50px;
        } */
        p{
            font-size: 10px;
        }
    }

    @media screen and (max-width: 800px) {
        p{
            font-size: 12px;
        }
    }

    @media screen and (min-width: 808px) {
        p{
            font-size: 14px;
        }
    }


    @keyframes fadin {
        0%{
            transform: translateY(10px);
            opacity: 0;
        }
        100%{
            transform: translateY(0px);
            opacity: 1;
        }
    }

</style>
<script>
  export default {
    name: "MeetingPage",
    props: {
        meetings: Object
    }
}
</script>

<template>
    <!-- <div class="box-meeting" :id="meetings.idMeeting">
        <div :class="{'circle-number-meeting': true}">
            <h2>{{ meetings.numberMeeting }}</h2>
        </div>

        <div class="box-content-meeting">
            <div class="content-meeting">
                <p>
                    {{ meetings.text[0] }}<br><br>

                    {{ meetings.text[1] }}<br><br>

                    {{ meetings.text[2] }}<br v-if="meetings.text.length >= 4"><br>

                    {{ meetings.text[3] }}
                </p>
            </div>


        </div>
    </div> -->
    <div class="box-meeting">
        <div class="box-content-meeting">
            <div class="content-meeting">
                <p>
                    {{ meetings.text[0] }}<br><br>

                    {{ meetings.text[1] }}<br><br>

                    {{ meetings.text[2] }}<br v-if="meetings.text.length >= 4"><br>

                    {{ meetings.text[3] }}
                </p>
            </div>
        </div>
    </div>
</template>

<style scoped>

    .box-meeting{
        min-height: 100vh;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        gap: 100px;
        background: rgb(20,86,94);
        background: v-bind('meetings.color');
        padding: 76px 0px;
        position: relative;
    }

    .circle-number-meeting{
        height: 80px;
        width: 80px;
        display: flex;
        justify-content: center;
        align-items: center;
        gap: 10px;

        background-color: white;
        /* border: 7px solid white; */
        box-shadow: 0px 0px 10px rgb(0 0 0);
        border-radius: 50%;
        position: relative;
        z-index: 2;
    }

    .circle-number-meeting::before{
        content: "";
        height: 40px;
        width: 40px;
        background-color: rgb(255, 255, 255);
        position: absolute;
        bottom: -8px;
        /* box-shadow: 0px 2px 20px rgb(0 0 0 / 69%); */
        transform: rotate(45deg);
        z-index: 1;
    }

    h2{
        font-size: 24px;
        color: #000000;
        z-index: 2;

    }

    .box-content-meeting{
        width: 100%;
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 70px;
    }

    .content-meeting{
        width: 50%;
        background-color: white;
        border-radius: 8px;
        padding: 12px 20px;
    }

    p{
        font-size: 18px;
    }

</style>
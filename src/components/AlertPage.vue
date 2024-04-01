<script>
  export default {
    name: "AlertPage",
    data() {
        return {
            signal: "x",
            fadinAnimation: true,
            fadeoutAnimation: false,
            circleAlert: "circle-alert"
        }
    },
    methods: {
        closeAlert() {
            this.fadinAnimation = false;
            this.fadeoutAnimation = true;
            setTimeout(() => this.$emit("close"), 970)

        }
    }
}
</script>

<template>
    <div class="box-alert">
        <div :class="{'box-text-alert' : true, 'fadin-animation' : fadinAnimation, 'fadeout-animation' : fadeoutAnimation}">
            <p class="text-alert">
                    Olá! Caso tenha aberto esta página sem qualquer informação prévia, 
                permita-me esclarecer a situação. Recentemente, passei 10 dias participando de um 
                curso do CIEE antes de começar a trabalhar na Jtech. Durante o curso, foi solicitado que 
                eu desenvolvesse um portfólio. Este portfólio deveria conter informações sobre o que aconteceu
                em cada dia e deveria ser feito utilizando Word, Canva ou PowerPoint. <br> <br>
                    Todavia, como não me dou muito bem com a elaboração de slides e, 
                caso eu fizesse um documento Word, provavelmente ficaria algo longo devido à minha 
                tendência de escrever muito quando tenho tempo. Sendo assim, aproveitei a oportunidade 
                para criar um site como portfólio para este curso e para praticar um pouco de Vue. 
                Além disso, pude testar alguns conceitos que queria colocar em prática há algum tempo.
            </p>
        </div>

        <div :class="{
            'circle-alert' : true, 
            'fadin-animation' : fadinAnimation, 
            'fadeout-animation' : fadeoutAnimation}"
            @click="closeAlert">
            <span>{{ signal }}</span>
        </div>
        <!-- <p>{{ alert }}</p> -->
    </div>
</template>

<style scoped>
    .box-alert{
        min-height: 100vh;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;        
        gap: 38px;
        background-color: #36474F;
    }


    .box-text-alert{
        width: 460px;
        background-color: white;
        border-radius: 15px;
        padding: 10px 10px;
        position: relative;
        box-shadow: 0px 1px 20px rgb(0 0 0 / 69%);
        z-index: 2;

    }

    .box-text-alert::before{
        content: "";
        height: 40px;
        width: 40px;
        background-color: rgb(255, 255, 255);
        position: absolute;
        right: 45.6%;
        bottom: -18px;
        /* box-shadow: 0px 2px 20px rgb(0 0 0 / 69%); */
        transform: rotate(45deg);
    }
    
    .text-alert{
        font-size: 14px;
    }
    
    .circle-alert{
        height: 48px;
        width: 48px;
        font-size: 32px;
        font-weight: 800;
        display: flex;
        align-items: center;
        justify-content: center;
        background-color: white;
        color: rgb(88, 23, 23);
        outline: 4px solid rgb(88, 23, 23);
        border-radius: 50%;
        box-shadow: 0px 1px 20px rgb(0 0 0 / 69%);
        /* outline: 4px solid rgb(158, 57, 57); */
        cursor: pointer;
        transition: 0.5s;
    }
    
    .circle-alert:hover{
        /* scale: 0.8; */
        color: rgb(146, 32, 32);
        outline: 4px solid rgb(146, 32, 32);
        box-shadow: 0px 1px 20px rgba(146, 24, 24, 0.69);
        transition: 0.5s;
    }

    .circle-alert:active{
        /* scale: 1; */
        color: rgb(0, 0, 0);
        outline: 4px solid rgb(0, 0, 0);
        transition: 0.2s;
    }

    .fadin-animation{
        animation: fadin 1s;
    }

    .fadeout-animation{
        animation: fadeout 1s;
    }

    @keyframes fadin {
        0%{
            transform: translateY(-10px);
            opacity: 0;
        }
        100%{
            transform: translateY(0px);
            opacity: 1;
        }
    }

    @keyframes fadeout {
        0%{
            transform: translateY(0px);
            opacity: 1;
        }
        100%{
            transform: translateY(-10px);
            opacity: 0;
        }
    }
</style>
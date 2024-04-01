<script>
  export default {
    name: "Welcome"
}
</script>

<template>
    <div class="box-welcome">
        <div class="circle-top-right"></div>
        <div class="circle-bottom-left"></div>
        <h1>Bem Vindo!</h1>
    </div>
</template>

<style scoped>
    .box-welcome{
        min-height: 100vh;
        display: flex;
        align-items: center;
        justify-content: center;
        position: relative;
    }

    .circle-top-right{
        height: 200px;
        width: 200px;
        background-color: white;
        border-radius: 0px 0px 0px 100%;
        box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.582);

        position: absolute;
        top: 0px;
        right: 0px;
    }

    .circle-bottom-left{
        height: 150px;
        width: 150px;
        background-color: white;
        border-radius: 0% 100% 0% 0%;
        box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.582);
        position: absolute;
        bottom: 0px;
        left: 0px;
    }

    h1{
        font-size: 62px;
        color: white;
        z-index: 2;
        animation: 1s fadin;
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
</style>
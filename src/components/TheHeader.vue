<script>
  export default {
    name: "TheHeader",
    data() {
        return {
            arrayEncontros: [
                "Primeiro", 
                "Segundo", 
                "Terceiro", 
                "Quarto", 
                "Quinto", 
                "Sexto", 
                "Setimo", 
                "Nono",
                "Decimo"
            ]
        }
    },
    props: ['openOptions'],
    computed: {
      // openOptions: false
    }
  }
</script>

<template>
  <header>
    <p class="title-header">Vue</p>
    <ul v-if="openOptions">
        <li class="dropdown"><a>Encontros</a><br>

          <ul class="itens-dropdown">
              <li v-for="encontro in arrayEncontros">
                <a :href="'#' + encontro">{{ encontro }}</a>
            </li>
          </ul>

        </li>

        <li><a href="#sobre">Sobre mim</a></li>
    </ul>
  </header>
</template>

<style scoped>
  header{
    height: 58px;
    width: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    position: fixed;
    /* background-color: rgb(214, 236, 255); */
    background-color: #43a5f6;
    color: white;
    padding: 0px 46px;
    box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.61);
    z-index: 100;
  }

  .title-header{
    font-size: 38px;
    font-weight: 600;
  }

  /* .itens-header{
    display: flex;
    align-items: center;
    gap: 20px;
  } */

  ul{
    height: 100%;
    display: flex;
    flex-direction: row;
    align-items: center;
    /* background-color: rgb(214, 236, 255); */
    background-color: #43a5f6;
    position: relative;
    animation: fadin 0.5s;
    transition: 0.5s;
  }

  li{
    height: 100%;
    width: 130px;
    display: flex;
    align-items: center;
    list-style: none;
    padding: 10px 10px;
    transition: 0.5s;
    position: relative;
  }

  li:hover{
    background-color: rgb(56, 114, 161);
    transition: 0.5s;
  }

    
  ul li a{
    font-size: 18px;
    text-decoration: none;
    color: #ffffff;
    transition: 0.5s;
  }

  ul li a:hover{
    color: #ffffff;
    transition: 0.5s;
  }

  .dropdown{
    display: flex;
    align-items: center;
  }

  ul li .itens-dropdown{
    height: 100%;
    display: flex;
    flex-direction: column;
    position: absolute;
    top: 58px;
    left: 0;
    display: none;
    transition: 0.5s;
  }

  .dropdown:hover .itens-dropdown{
    display: block;
    transition: 0.5s;
  }

  ul li .itens-dropdown li{
    height: 70%;
    background-color: #445964;
    box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.61);
  }

  ul li .itens-dropdown li:hover{
    background-color: #63808f;
  } 

</style>

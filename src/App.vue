<script>
  import AlertPage from "./components/AlertPage.vue"
  import Sidebar from "./components/Sidebar.vue"

  export default {
    name: "App",
    components: { AlertPage, Sidebar },
    data() {
      return {
        alertOpen: true,
        openPages: false,
        meetings: [
          {
            numberMeeting: 1, 
            idMeeting: "Primeiro",
            color: "linear-gradient(90deg, rgba(11,88,142,1) 0%, rgba(11,102,142,1) 24%, rgba(0,176,255,1) 95%)",
            text: [
              `Bem, meu primeiro dia de curso foi relativamente tranquilo, pois no começo da 
              aula ao vivo, a professora nos instruiu bem sobre como seria o curso, como iríamos 
              realizar ele e que teríamos grande parte do conteúdo numa plataforma do CIEE e o resto 
              seria em algumas aulas online como aquela.`,

              `Após o fim da aula, fui acessar a plataforma e tive mais algumas explicações 
              similares às que a professora nos deu no início da aula, todavia, o conteúdo ao 
              todo dessa aula era sobre a Lei de Aprendizagem, criada anteriormente em 2000.`,

              `Tal lei teve a finalidade de fomentar a inserção de jovens do mercado do 
              trabalho e proteger esses mesmos jovens de lugares perigosos que poderiam 
              afetar diretamente o desenvolvimento do indivíduo, além de possibilitar uma 
              jornada de trabalho que possibilitava tanto o estudo da escola quanto o 
              desenvolvimento profissional dos jovens.`,

              `Ela em si teve inúmeros benefícios, todavia, é bom comentar que a elaboração dessa
              lei só foi possível por causa do ECA (Estatuto da Criança e do Adolescente), isto 
              pois este estatuto definiu os direitos das crianças e adolescentes, como por exemplo,
              a obrigação da sociedade prezar pela proteção do desenvolvimento físico, intelectual, 
              afetivo, social e cultural desses indivíduos.`
            ]
          },
          {
            numberMeeting: 2, 
            idMeeting: "Segundo",
            color: "linear-gradient(90deg, rgba(16,111,173,1) 0%, rgba(64,213,241,1) 48%, rgba(40,119,144,1) 100%)",
            text: [
              `Nesse encontro aprendemos tanto sobre os direitos e deveres dos trabalhadores quanto
              dos empregadores. Foi nos ensinado que CLT foi criada com o intuito juntar todas as 
              leis que falavam sobre essa respetiva questão num lugar só, todavia, vale ressaltar que 
              anteriormente essas questões estavam espalhadas aos setes mares da nossa legislação, logo,
              era extremamente complicado saber apropriadamente todos os direitos dos trabalhadores e
              até mesmo dos empregadores.`,

              `Uma vez que esta organização foi elaborada, ficou mais fácil consultar as leis vigentes
              e aplicar as mesmas. Além de apreendemos sobre este cenário, também aprendemos sobre 
              algumas dessas leis, que por antes de serem definidas, acarretava numa situação totalmente 
              desumana de viver, como ter que ficar 16 horas seguidas todos os dias sem até mesmo um 
              minuto de intervalo. Ao criarmos leis que protegem os trabalhadores dessas situações, 
              conseguimos pelo menos reverter cenários tenebrosos como estes. `,

              `Algumas leis que ajudaram a amenizar esses cenários na minha opinião foram tanto a lei que 
              determina um limite máximo de quanto alguém poderia trabalhar quanto a lei que define o 
              descanso obrigatório e o pagamento de hora extra caso.`
            ]
          },
          {
            numberMeeting: 3, 
            idMeeting: "Terceiro",
            color: "linear-gradient(90deg, rgba(4,107,126,1) 0%, rgba(0,155,255,1) 39%, rgba(0,231,252,1) 100%)",
            text: [
              `Esse encontro em si foi focado em uma empresa, no entanto, podemos dividir esse tema em 
              três tópicos diferentes. O primeiro abordou o conceito de empresa, seus tipos e como 
              se encaixava na nossa sociedade, já o segundo abordou conceitos que chamaram mais a minha 
              atenção do que o terceiro, que foi organograma de uma empresa, no caso o que a atenção foi 
              os conceitos de missão, visão e valores. `,

              `Tal conceitos fizeram muito sentido para mim, uma vez que no meu entendimento de como se 
              criava um negócio, era necessário primeiramente que criássemos uma solução para um problema 
              que causava algumas complicações na vida de algum indivíduo ou empresa.`,

              `Nesse contexto, a elaboração de uma missão provavelmente seria mais fácil porque já 
              teríamos definido o porquê aquela empresa foi feita, todavia é essencial termos uma 
              visão para não nos perdemos no meio do caminho. No caso, onde especificamente essa 
              empresa deseja estar no futuro, basicamente um objetivo pela qual sempre almeja. `,

              `Além disso, é preciso determinar os valores que esta nova empresa preza, pois
              assim já saberíamos que tipo de cultura queremos incentivar para se desenvolver 
              nesta organização, além de que isso ajudaria a filtrar o perfil de pessoa com quem 
              desejamos trabalhar. `
            ]
          }
        ]
      }
    },
    methods : {
      closePageAlert() {
        this.alertOpen = false;
        this.openPages = true;
      }
    }
  }
</script>

<template>
  <div class="container">
    <AlertPage v-if="alertOpen" @close="closePageAlert"/>
    <Sidebar v-if="openPages"/>
  </div>
</template>


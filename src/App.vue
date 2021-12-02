<template>
  <div id="app">
      <!--REMARQUE: On pourrais le mettre dans un component enfant et passer ses variables avec $emit etc.. au parent, puis du parent à la small card-->
      <!--Pour les variables et les fonctions donner le nom de ce qu'ils font-->
      <!--Boucler direct sur l'appel du smallCard au lieu de boucler dans le component-->

      <div class="flex mt-20">
      <!--BigCard-->
      <BigCard @getBtnValue="btnVal" />
      <!--SmallCard Component btnType va chez l'enfant-->
      <div class="grid grid-cols-3 gap-4 ml-5 small " >
      <SmallCard :timeframes='btnValue' v-for='data in datas' :key="data.title" :dataObj='data' />
      <!--Une autre smallCard sera créé si on rajoute des données dans le json OU si on l'appel a part pour l'inserer totalement ailleurs, dans ce cas il faudra creer un objet dataObj afin de respecter la structure de donnée de la carte a sa création-->
      
      </div>
      </div>
    
  </div>
</template>

<script>
import SmallCard from "./components/SmallCard.vue";
import BigCard from "./components/BigCard"
//import du json.On lui donne le nom qu'on veut
import jsonDatas from '../exo-ressources/data.json'

export default {
  name: "App",
  components: {
    SmallCard,BigCard
  },
  data() {
    return {
      btnValue:'daily',
      datas: jsonDatas
    }
  },
  methods: {
    btnVal(value){
      console.log(value)
      this.btnValue=value
    }
  },
};
</script>

<style lang="scss">
html {
  background-color: hsl(226, 43%, 10%);
}
.small{
  margin-top: 12%
}

</style>

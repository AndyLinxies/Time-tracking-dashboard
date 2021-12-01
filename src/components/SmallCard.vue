<template>
  <div class='mt-32'>
    <!--Montre les infos de Daily quand on clique sur daily v-if='pressedBtn == "daily" '-->
    <div  class="grid grid-cols-3 gap-4 ml-5">
    <div  class="work rounded-xl pl-5 pt-3 text-white" v-for='data,index in datas' :key="index" >
      <p>{{data.title}}</p>
      <!--Infos curent Daily Weekly Monthly-->
        <p class='text-5xl'>{{
            pressedBtn == "daily"? data.timeframes.daily.current : 
            pressedBtn == "weekly"? data.timeframes.weekly.current : 
            pressedBtn == "monthly"? data.timeframes.monthly.current :null
            }} hrs</p>

        <!--Infos last week-->
        <p>Last week- {{
            pressedBtn == "daily"? data.timeframes.daily.previous : 
            pressedBtn == "weekly"? data.timeframes.weekly.previous : 
            pressedBtn == "monthly"? data.timeframes.monthly.previous :null
        }} hrs</p>
      </div> 
    </div>
    <!--Montre les infos de Weekly quand on clique sur weeky-->
    
  </div>
</template>
<script>
import jsonDatas from '../../exo-ressources/data.json'

export default {
  name: "SmallCard",
  props:{
    pressedBtn: String
  },
  data() {
      return {
          datas: jsonDatas
      }
  },
};
</script>
<style lang="scss" scoped>
.work{
    height:150px;
    width: 200px;
    background-color:  hsl(235, 46%, 20%);
    
}
</style>

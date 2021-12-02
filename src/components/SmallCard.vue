<template>
  <div class='avWork'>
    <!--Montre les infos de Daily quand on clique sur daily v-if='pressedBtn == "daily" '-->
    <div  class="work rounded-xl pl-5 pt-3 text-white" >
      <p>{{dataObj.title}}</p>
      <!--Infos curent Daily Weekly Monthly-->
        <p class='text-5xl'>{{
            timeframes == "daily"? dataObj.timeframes.daily.current : 
            timeframes == "weekly"? dataObj.timeframes.weekly.current : 
            timeframes == "monthly"? dataObj.timeframes.monthly.current :null
            }} hrs</p>

        <!--Infos last week-->
        <p>Last week- {{
            timeframes == "daily"? dataObj.timeframes.daily.previous : 
            timeframes == "weekly"? dataObj.timeframes.weekly.previous : 
            timeframes == "monthly"? dataObj.timeframes.monthly.previous :null
        }} hrs</p>
      </div> 
    </div>
    <!--Montre les infos de Weekly quand on clique sur weeky-->
    
  
</template>
<script>
// import jsonDatas from '../../exo-ressources/data.json'

export default {
  name: "SmallCard",
  props:{
    pressedBtn: String,
    timeframes: String,
    dataObj: Object,

  },
  data() {
      return {
          
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
.avWork{
  
}
</style>

<template>
    <div >
      
    <!--BigCard-->
      <div
        class="bg-gray-100 items-center justify-center bigCard rounded-xl ml-20"
      >
        <div class="pt-10 ml-8">
          <img src="../assets/images/image-jeremy.png" width="90px" alt="" />
        </div>

        <div class="p-5">
          <p class="mt-2 text-sm text-gray-600">Report for</p>
          <p class="mt-1 text-gray-500 text-xl">
            JEREMY <br/>
            ROBSON
          </p>
        </div>
        <div class="under rounded-xl">
          <div class="pt-10 pl-10 text-blue-500">

            <!--multiple conditions in :class-->
            <button :class="{'text-white':clicked ==true && btnType=='daily'}  " @click="getClick('daily')">Daily</button><br />

            <button :class="{'text-white':clicked ==true && btnType=='weekly'}  " @click="getClick('weekly')">Weekly</button><br />

            <button :class="{'text-white':clicked ==true && btnType=='monthly'}  " @click="getClick('monthly')">Monthly</button><br />
          </div>
        </div>
      </div>
    </div>
</template>
<script>

export default {
    name: 'BigCard',
    data() {
        return {
            clicked: false,
            btnType: "daily",
        }
    },
    methods: {
    getClick(value) {
      this.btnType = value;
      this.clicked=true;
    // console.log(this.btnType);
    //Passage du btnType au parent puis après au SmallCard
    this.$emit('getBtnValue',this.btnType)
    
    },
    },
}
</script>

<style lang="scss" scoped>
.bigCard {
  width: 300px;
  height: 450px;
  background-color: hsl(246, 80%, 60%);
}
.under {
  background-color: hsl(235, 46%, 20%);
  height: 200px;
}
</style>
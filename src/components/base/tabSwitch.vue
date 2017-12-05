<template>
  <div id="tabSwitch">
    <div class="header">
      <ul>
        <li
          v-for="(item,index) in tabs"
          :class="{active:index == num}"
          @click="tab(index)">{{item}}</li>
      </ul>
    </div>
    <div class="tabCon">
      <div
        v-for='(itemCon,index) in tabContents'
        v-show=" index == num">{{itemCon}}
      </div>
    </div>
  </div>
</template>
<script >
  export default {
    name: 'tabSwitch',
    data(){
      return{
        tabs: ["标题一", "标题二", "标题三"],
        tabContents: ["内容一", "内容二", "内容三"],
        num: 1
      }
    },
    methods: {
      tab(index) {
        this.num = index;
      }
    }
  }
</script>
<style scoped>
  #tabSwitch{
    margin-top: 40px;
    height: 300px;
    background-color: white;
    margin-left: 10px;

  }
  .header{
    height: 20px;
  }
  #tabSwitch ul li{
    float: left;
    width: 60px;
    height: 20px;
    border: 1px solid #000;

  }
  .active{
    color: red;
  }
  .tabCon{
    margin-top: 40px;
    height: 200px;
    width: 200px;
    color:blue;
    border: 1px solid #000;
  }
</style>

<template>
    <div id="tabSwitch">
      <ul>
        <li
          v-for="(item,index) in tabs"
          :class="{active:index == num}"
          @click="tab(index)">{{item}}</li>
      </ul>
      <div class="tabCon">
        <div
          v-for='(itemCon,index) in tabContents'
          v-show=" index == num">{{itemCon}}</div>
      </div>
    </div>
</template>
<script type="text/javascript">
  export default {
          data: {
            tabs: ["标题一", "标题二","标题三"],
            tabContents: ["内容一", "内容二","内容三"],
            num: 1
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
  }
  ul{
    height: 300px;
  }
  .active{
    color: red;
  }
</style>

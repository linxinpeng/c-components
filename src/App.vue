<!--
 * @Descripttion: 
 * @version: 
 * @Author: linxp
 * @Date: 2020-08-12 14:40:19
 * @LastEditors: linxp
 * @LastEditTime: 2020-08-12 15:38:53
-->
<template>
  <div id="app">
      <div class="x-flex">
        <SelectBox :active.sync="active">
          <div style="height: 100px;width: 100px; background: #409EFF;"></div>
        </SelectBox>
      </div>
  </div>
</template>

<script>
import SelectBox from "./components/select-box"
export default {
  name: 'App',
  components: {
    SelectBox
  },
  data(){
    return{
      active: false
    }
  }
}
</script>

<style>
#app{
  width: 1300px;
  margin: 20px auto;
}
.x-flex{
  display: flex;
  align-items: center;
}
</style>

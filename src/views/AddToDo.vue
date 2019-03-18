<template>
  <div class="content-box">

     <div class="my-inputbox">
        <textarea name="my-inputbox" rows="10" v-model="toDoContent" placeholder="-请填写内容"></textarea>
        <button type="button">确定</button>
     </div>

     <div class="my-content-list">
       <span v-for="(item, index) in toDoContentList" :key="index">{{item}}</span>
     </div>

  </div>
  
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';

@Component({
  components: {
  },
})
export default class AddToDo extends Vue {
 
 public contentItem = {content:'',date:''};// 个体对象

 public toDoContentList:any = []; //列表内容


 


}
</script>

<style lang="scss" scoped>

.content-box{
  display: flex;
  justify-content: space-between;
}

.my-inputbox{
  width: 45%;

  textarea{
    width: 100%;
    border: 1px solid #cccccc;
    padding: 15px;
    font-size: 16px;
    outline: none;
  }
}

.my-content-list{
  width: 45%;
  text-align: left;
}

 .my-addButton{
   
 }
</style>


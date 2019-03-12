<template>
  <div class="home">
    <HelloWorld msg="Welcome to Your Vue.js + TypeScript App"/>
    <div>
      {{ testValue }}
    </div>
    <div>
      <button type="button" onclcik="addNum()">测试按钮事件</button>
    </div>
    <div>{{content}}</div>

    <div class="content-box">
       <div v-for="(item, index) in contents" :key="index" class="content-item">
         {{ item }}
       </div>
       </div>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import HelloWorld from '@/components/HelloWorld.vue'; // @ is an alias to /src

@Component({
  components: {
    HelloWorld,
  },
})
export default class Home extends Vue {

 public testValue = 1;
 public content = '内容显示';
 public contents = [
   'TOM','HURRY','JONE','PIPEN','JORDEN'
 ]

 public addNum() {
  this.testValue++;
  console.log(this.testValue);
 }


}
</script>

<style lang="scss" scoped>
  .content-box{
    display:flex;
    width: 800px;
    justify-content: left;
    margin: 0 auto;
  }
 
 .content-item{
    box-sizing: border-box;
    flex-basis: 100px;
    border:1px solid #cccccc;
    padding: 15px;
    margin: 10px;
    flex-grow: 3;
 }

</style>


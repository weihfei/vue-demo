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


 public addNum() {
  this.testValue++;
  console.log(this.testValue);
 }


}
</script>

<template>
  <div class="content-box">

     <div class="my-inputbox">
        <textarea name="my-inputbox" rows="10" v-model="inputToDoContent" placeholder="-请填写内容"></textarea>
        <button type="button" id="confim" v-on:click="getCount()">确定</button>
        <label for="confim">确定</label>
     </div>

     <div class="my-content-list">
        <div v-for="(item, index) in toDoContentList" :key="index" class="content-item" v-bind:style="{background:randomColor[Math.round(Math.random()*randomColor.length-1)]}">
           <span>{{index+1+'.'}} {{item.content}}</span>
           <span>{{item.date}} <i v-on:click="removeList(index)">X</i></span>
        </div>
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
 public contentItem = {content: '', date: ''}; // 个体对象
 public inputToDoContent = ''; // 输入内容
 public toDoContentList: any = []; // 列表内容
 public bgColor: any;
 public randomColor = ['#ff2c2c', '#ff802c', '#ffd82c', '#9cdb69', '#69db9c', '#69cedb', '#b5c7f8', '#dab5f8', '#e694d8']; // 保存随机颜色

public getCount(): void {
  if (this.inputToDoContent) {// 将填写的内容保存进入数组，用来显示
    this.getRandomColor();
    this.toDoContentList.push({content: this.inputToDoContent, date: new Date().toLocaleString()});
    this.inputToDoContent = ''; // 将文本域的内容置为空
  }
}

// 生成随机颜色
public getRandomColor() {
  // let colorArray = []; // 申明一个保存颜色的数组
  // for(let i=0; i<3; i++) {
  //   colorArray.push(Math.round(Math.random()*255));
  // }
  //  this.randomColor=`rgb(${colorArray[0],colorArray[1],colorArray[2]})`
  //  this.bgColor = {
  //    background:this.randomColor
  //  }
  //  console.log('打印随机颜色',colorArray);

  this.bgColor = this.randomColor[Math.round(Math.random() * this.randomColor.length)];
  console.log(this.bgColor, Math.round(Math.random() * this.randomColor.length));
}

// 删除列表项
public removeList(I: number) {
  this.toDoContentList.splice(I, 1);
}

}
</script>

<style lang="scss" scoped>

.content-box{
  display: flex;
  justify-content: space-between;
}

.my-inputbox{
  width: 30%;

  textarea{
    width: 100%;
    border: 1px solid #cccccc;
    padding: 15px;
    font-size: 16px;
    outline: none;
    resize: none;
  }

  button{
    position: absolute;
    clip: rect(0,0,0,0);
  }

  label{
    display: inline-block;
    line-height: 20px;
    padding: 10px 45px;
    border: 1px solid #cccccc;
    background: #dfdfdf;
    cursor: pointer;
    margin: 10px auto;
    transition: all .5s linear;
    &:hover{
      background: #eeeeee;
      transition: all .5s linear;
    }
  }
}

.my-content-list{
  width: 65%;
  text-align: left;
  // counter-reset: contentList;
  max-height: 350px;
  overflow-y: auto;
}

.content-item{
  display: flex;
  padding: 15px 20px;
  justify-content: space-between;
  margin: 10px auto;
  cursor: pointer;
  span:last-child{
    justify-content: right;
  }
  i{
    border: 1px solid #353535;
    color: #353535;
    border-radius: 25px;
    padding: 2px 8px;
    margin-left: 10px;
  }
}

// .content-item::before{
//   content: counter(contentList) '.';
//   counter-increment: contentList;
// }


</style>


<template>
  <div id="app">
    <!-- <FloatLabel placeholder="false">
      <input v-model="myValue" placeholder="xixiu" on="false" />
    </FloatLabel>
    
    <my-input v-model="myValue" placeholder="姓名" class="AA" />
    <br />
    <el-input v-model="myValue" placeholder="sssss"></el-input> -->
    <el-form :model="list">
      <el-form-item label="ssss" label-width="100px">
        <el-input v-model="myValue" placeholder="dddddf"></el-input>
      </el-form-item>
    </el-form>
    <my-select placeholder="my-Select"></my-select>
    <el-select v-model="myValue3" placeholder="">
      <el-option v-for="itm in [1,2,3,4]" :key="itm" :label="itm"></el-option>
    </el-select>
    <select style="width:100px">
      <option value="sssss">sssss</option>
      <option value="ssss1">ssss1</option>
      <option value="ssss2">ssss2</option>
      <option value="ssss3">ssss3</option>
    </select>
    <mu-text-field v-model="myValue" disabled placeholder="ssdddd"></mu-text-field>
    <el-card style="width:500px;margin-left:400px">
      <my-input v-model="myValue6" placeholder="登录名" class="AA" />
      <br />
      <my-input v-model="myValue5" placeholder="密码" labelWidth="50px" class="AA" />
      <br />
      <my-input v-model="myValue4" placeholder="验证码" :disabled="true"  class="AA" />
      <br />
    </el-card>
    <el-card style="width:500px;margin-left:400px">
      <my-input v-model="myValue3" placeholder="登录名" labelPosition="top" class="AA" />
      <br />
      <my-input v-model="myValue2" placeholder="密码" labelPosition="top" class="AA" />
      <br />
      <my-input v-model="myValue1" placeholder="验证码" labelPosition="top" class="AA" />
      <br />
    </el-card>
  </div>
</template>

<script>
import FloatLabel from "./floatLabel";
import MyInput from "./components/myInput";
import MySelect from "./components/mySelect"

export default {
  name: "App",
  components: {
    FloatLabel,
    MyInput,
    MySelect,
  },
  data() {
    return {
      list:{},
      myValue: "",
      myValue1: "",
      myValue2: "",
      myValue3: "",
      myValue4: "",
      myValue5: "",
      myValue6: "",
    };
  },
  updated() {
  },
};
</script>

<style scoped lang="stylus">
.AA
  margin-left: 100px
  width: 300px
#app
  font-family: Avenir, Helvetica, Arial, sans-serif
  -webkit-font-smoothing: antialiased
  -moz-osx-font-smoothing: grayscale
  text-align: center
  color: #2c3e50
  margin-top: 60px
</style>

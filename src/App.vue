<template>
  <div id="app">
    <!-- <FloatLabel placeholder="false">
      <input v-model="myValue" placeholder="xixiu" on="false" />
    </FloatLabel>
    
    <my-input v-model="myValue" placeholder="姓名" class="AA" />
    <br />
    <el-input v-model="myValue" placeholder="sssss"></el-input>
    <mu-text-field v-model="myValue"></mu-text-field>-->
    <el-card style="width:500px;margin-left:400px">
      <my-input v-model="myValue6" placeholder="登录名" class="AA" />
      <br />
      <my-input v-model="myValue5" placeholder="密码" class="AA" />
      <br />
      <my-input v-model="myValue4" placeholder="验证码" class="AA" />
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

export default {
  name: "App",
  components: {
    FloatLabel,
    MyInput,
  },
  data() {
    return {
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

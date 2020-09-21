<template>
  <div class="home">

    <el-row type="flex">
      <el-col :span="5">
        用户名:<el-input v-model="uname" placeholder="请输入内容"></el-input>
        密码：<el-input placeholder="请输入密码" v-model="pwd" show-password></el-input>
        <el-button type="primary" @click="test">登录</el-button>
      </el-col>
        
    </el-row>

  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'Home',
  data() {
    return {
      uname: '',
      pwd: ''
    }
  },
  methods: {
    // 测试接口函数
    test () {
      this.axios.post(`api`,{
        uname: this.uname,
        pwd: this.pwd
      }).then(res => {
        console.log(res);
      })
    }
  },
  components: {
  }
}
</script>

<style scoped>

  .el-button {
    margin: 20px 150px;
  }
  
</style>

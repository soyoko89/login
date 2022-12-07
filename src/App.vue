<template>
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
</template>



<script>
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
      ElMessage({
        message: 'Амжилттай нэвтэрлээ...',
        type: 'success',
      })
    }
  }
}
</script>
<style scoped>
body {
 width: 100vh;
 height: 100vh;
 background-image: url("./assets/backgroundImage.jpg");
 background-color: #cccccc;
 background-size: cover;
 justify-content: center;
}
</style>

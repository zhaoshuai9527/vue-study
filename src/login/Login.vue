<template>
  <!--flex弹性盒子模型，justify-content：主抽 -->
  <el-container>
  <el-card class="el-card">
    <div>
      <span>登 录</span>
    </div>

    <table>
      <tr>
        <td>用户名</td>
        <td>
          <el-input v-model="user.username" placeholder="请输入用户名"></el-input>
        </td>
      </tr>
      <tr>
        <td>密码</td>
        <td>
          <el-input type="password" v-model="user.password" placeholder="请输入密码"
                    @keydown.enter.native="doLogin"></el-input>
          <!-- @keydown.enter.native="doLogin"当按下enter键的时候也会执行doLogin方法-->
        </td>
      </tr>
      <tr>
        <!-- 占两行-->
        <td colspan="2">
          <!-- 点击事件的两种不同的写法v-on:click和 @click-->
          <!--<el-button style="width: 300px" type="primary" v-on:click="doLogin">登录</el-button>-->
          <el-button style="width: 300px" type="primary" @click="doLogin">登录</el-button>
        </td>
      </tr>
    </table>
  </el-card>
  </el-container>
</template>

<script>
    export default {
        name: "Login",
        data() {
            return {
                user: {
                    username: '测试',
                    password: '123456789'
                }
            }
        },
        methods: {
            doLogin() {
                alert(JSON.stringify(this.user))
            }
        }
    }
</script>

<style scoped>
.el-card{
  width: 500px;
  height: 400px;
}
</style>

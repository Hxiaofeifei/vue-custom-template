<template>
    <div class="body">
        <div class="modal">
            <div class="input"> 
                <el-input
                    placeholder="请输入用户名"
                    v-model="user"
                    prefix-icon="iconfont icon-UserSettings"
                >
                 </el-input>
            </div>

           <div class="input">
                <el-input
                    placeholder="请输入密码"
                    v-model="password"
                    type="password"
                    prefix-icon="iconfont icon-suo"
                >
                </el-input>
           </div>
            <div class="forgetPwd">
                <div>忘记密码?</div>
                <div>注册</div>
            </div>
            <div class="btn" @click="onLogin()">
                登 录
            </div>
            <div>{{this.resLogin.id || "123"}}</div>

           <!-- <el-button type="primary" class="btn" >登录</el-button> -->
        </div>

    </div>
    
</template>
<script>
import {mapActions,mapGetters} from "vuex";
export default {
    data() {
        return {
           user:"admin",
           password:"123456"
        };
    },
    computed: {
        ...mapGetters(['resLogin']),
        // resLogin(){
        //     return 
        // }

        //console.log()

            

    },
    watch:{
        resLogin(newstate,oldstate){
            console.log(oldstate,"old")
            console.log(newstate,"new")
            if(e.id=="123"){

             //this.$router.push("/")
            }      
        }
    },
    methods: {

     ...mapActions([
         'reqLogin'
      ]),
       onLogin(){
           this.$router.push("/")
        //    let data = {
        //         user:this.user,
        //         password:this.password
        //    }
        //    sessionStorage.setItem("userInfo",data)
        //    this.reqLogin(data)
           //this.$store.dispatch("reqLogin",data)
           //
           //this.reqLogin({id:123,name:"小飞飞"})
           
       }
    },
    beforeUpdate(){
        console.log(this.resLogin,"resLogin===============>之前")
    },
    updated(e){
        console.log(this.resLogin,"resLogin===============>")
    }
};
</script>
<style scoped >
    .body {
        display: flex;
        flex: 1;
        flex-direction: row;
        width: 100%;
        height: 100vh;
        background: url("../image/lockLogin.png") no-repeat 20% 30%;
        justify-content: flex-end;
    }
    .modal{
        width: 400px;
        height:300px;
        box-shadow: 5px 5px 20px #808080;
        border-radius: 10px;
        display:flex;
        flex-direction: column;
        align-items: center;
        margin-top: 100px;
        margin-right: 100px;
        padding: 20px 20px 0 20px;
        box-sizing: border-box;
    }
    .input{
        display: flex;
        flex-direction: row;
        width: 100%;
        margin-top: 30px;
    }
    .input >span{
        width: 150px;
        text-align: center;
        display: flex;
        align-items: center;
        justify-content: center;
    }
    .btn{
        width: 100%;
        border: 1px solid #808080;
        height: 40px;
        border-radius: 20px;
        margin-top: 20px;
        line-height: 40px;
        text-align: center;
        cursor: pointer;
    }
    .btn:hover{
        background:#fff;
        opacity: 0.8;
    }

    .forgetPwd{
        display: flex;
        flex-direction: row;
        width: 100%;
        justify-content: space-between;
        font-size: 14px;
        color:#333;
        margin-top: 10px;

    }
    .forgetPwd>div{
        cursor: pointer;
    }
    .forgetPwd>div:hover{
        color:#808080;
    }

</style>


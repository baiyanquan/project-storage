<template>  
    <div class="main_bg" :style="{backgroundImage: 'url(' + bgImg + ')' }" style="height: 740px;width:100%">
        <!--导航--> 
        <div class="main-topbar">
            <el-row >
                <el-col :span="3">
                    <div class="topbar_title">
                        <img :src="logo_small"/>
                    </div>
                </el-col>
                 <el-col :span="18" >
                     <div >
                <el-menu :default-active="activeIndex"  mode="horizontal" @select="handleSelect"
                            background-color=rgba(0,0,0,0) text-color="#fff"  active-text-color="#ffd04b">
                  <el-menu-item index="1" @click="homepage">主页</el-menu-item>
                  <el-menu-item index="2" @click='feature'>简介</el-menu-item>
                  <el-menu-item index="3" @click="price">定价</el-menu-item>
                </el-menu>
                 </div>
                </el-col>
                <!--登录--> 
                <el-col :span="3">
                    <p style="margin-left:60px;">
                        <el-button  @click="login" style="background-color:rgba(255,255,255,0.3);color:#fff;width:80px;">
                        登录
                        </el-button></p>
                </el-col>
            </el-row>  
        </div><!--topbar end--> 
      
        
        <div class="main_reg">
            <el-row type="flex" justify="center">
                <el-col :span="6">   
                    <div style="text-align: center;"  >
                        <div style="margin:0 auto;">
                            <h1 style="color:#fff"><img :src="logo"></h1>   
                            
                            <el-button class="register_button" @click="register">现在注册加入TJ众测平台</el-button>
                        </div>
                    </div>
                    
                </el-col>
            </el-row>
        </div>
    
    
    </div>
</template>

<script scoped>
    export default {
        methods: {
            login () {
                this.$router.push('/login')
            },
            register(){
                this.$router.push('/register')
            },
            homepage(){
                this.$router.push('/')
            },
            feature(){
                this.$router.push('/main_feature')
            },
            price(){
                this.$router.push('/main_price')
            }
        },
        data(){
            return{
                bgImg:require("../../static/bg.jpg"),
                logo:require('../../static/logo_white_big.png'),
                logo_small:require('../../static/logo_white.png'),
                activeIndex:'1'
            }
        }
    }
</script>

<style>
.main_reg{
    margin-top: 100px;
}
.topbar_title{
    color:#fff; 
    margin-left:30px;
    margin-top: 15px;
    font-size: 70%;
}
.el-button--primary{
    margin-left: 40px;
}
.register_button{
    width: 250px;
    height: 50px;
    font-size: 17px;
}
</style>



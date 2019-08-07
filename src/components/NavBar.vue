<template>
    <!--navbar-->
    <div class="navbar">
        <div class="container">
            <div class="header-menu">
                <a href="https://job.alibaba.com/zhaopin/index.htm" class="logo left">
                    <img src="../assets/logo.png" alt="logo">
                </a>
                <i class="left line">|</i>
                <i class="left society">社招官网</i>
                <!--导航标签-->
                <ul class="menu">
                    <li class="link-item left">
                        <a href="https://job.alibaba.com/zhaopin/index.htm" class="link active">首 &nbsp;&nbsp;页</a>
                    </li>
                    <li class="link-item left">
                        <a href="https://job.alibaba.com/zhaopin/positionList.htm" class="link">社会招聘</a>
                    </li>
                    <li class="link-item left">
                        <a href="https://campus.alibaba.com/index.htm" class="link">校园招聘</a>
                    </li>
                    <li class="link-item left">
                        <a href="https://job.alibaba.com/zhaopin/about.htm" class="link">了解阿里</a>
                    </li>
                    <li class="link-item left">
                        <a href="https://auth.alipay.com/login/index.htm" class="link">个人中心</a>
                    </li>
                    <div class="login">
                        欢迎来到阿里巴巴集团招聘！
                        <a href="#" target="_top">登录</a> |
                        <a href="#">注册</a>
                    </div>
                </ul>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'navbar'
    }
</script>

<style scoped>
.navbar {
    height: 54px;
    background: #2C2F33;
    text-align: right;
}

.header-menu {
    opacity: .8;
    height: 54px;
}

.navbar .logo,
.logo img {
    height: 20px;
    width: 125px;
}

.left {
    float: left;
}

.logo {
    display: block;
    margin-top: 16px;
}

.header-menu .line {
    font-style: normal;
    font-size: 20px;
    line-height: 52px;
    margin: 0 10px;
}

.header-menu .society {
    font-style: normal;
    font-size: 14px;
    line-height: 54px;
}

/*=======导航标签======*/
.header-menu .menu {
    list-style: none;
    margin: 0;
}

.header-menu .link-item {
    position: relative;
    z-index: 2;
    cursor: pointer;
}

.header-menu .link  {
    font-size: 14px;
    line-height: 52px;
    padding: 10px 15px;
    margin-left: 4px;
    text-decoration: none;
    color: #fff;
}

.menu .active {
    color: #F37327;
}

.menu .link:hover {
    color: #F37327;
}

/*=======登录注册======*/
.header-menu .login {
    width: 340px;
    float: right;
    line-height: 52px;
    text-align: right;
}

.login > a {
    text-decoration: none;
    color: #fff;
}

</style>

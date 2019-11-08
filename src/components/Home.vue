<template>
    <div class="home">
        <div class="title">
            <div class="left">
                美团充换电平台方后台管理系统</div>
            <div class="right">
                <el-button type="text">修改密码</el-button>
                <el-button type="text">退出登录</el-button>
            </div>
        </div>
        <div class="container">
            <img src="../assets/u1649.png" alt="">
            <el-tabs :tab-position="tabPosition">
                <el-tab-pane label="客户账号列表">客户账号列表
                    <CustomerList />
                </el-tab-pane>
                <el-tab-pane label="商家账号管理">商家账号管理</el-tab-pane>
                <el-tab-pane label="电池管理">电池管理</el-tab-pane>
                <el-tab-pane label="运维商管理">运维商管理</el-tab-pane>
                <el-tab-pane label="分销">分销</el-tab-pane>
                <el-tab-pane label="充值设置">充值设置</el-tab-pane>
                <el-tab-pane label="纠纷处理">纠纷处理</el-tab-pane>
            </el-tabs>
            <div class="setup">
                <i class="el-icon-s-tools">设置</i></div>
        </div>

    </div>
</template>

<script>
    import CustomerList from "../components/CustomerList.vue";
    export default {
        name: "home",
        components: {
            CustomerList
        },
        data() {
            return {
                tabPosition: 'left'
            };
        }
    };
</script>

<style>
    .home .title {
        background-color: #4057e8;
        display: flex;
        justify-content: space-between;
        color: #fff;
        padding: 20px;
        align-items: center;
    }

    .home .title button {
        color: #fff;
        margin-left: 10px;
    }

    .el-tabs--left {
        height: 600px;
    }

    .home .container img {
        width: 61px;
        height: 52px;
        margin: 10px 20px 0 36px;
    }

    .home .container{
        position: relative;
    }
    .home .setup {
        position: absolute;
        top: 600px;
        left: 40px;
        cursor: pointer;
    }
</style>
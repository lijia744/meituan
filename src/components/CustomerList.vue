<template>
    <div class="customerlist">
        <div class="search">
            <el-input v-model="input" placeholder="请输入查询条件"></el-input>
            <el-button type="primary">查询</el-button>
        </div>
        <div class="list">
            <el-table :data="tableData" stripe style="width: 100%">
                <el-table-column prop="name" label="用户名" width="180">
                </el-table-column>
                <el-table-column prop="date" label="注册时间" width="180">
                </el-table-column>
                <el-table-column prop="deposit" label="押金状态">
                    <template slot-scope="scope">
                        <span v-if="scope.row.deposit=='未缴纳'" style="color:#e7414d">未缴纳</span>
                        <span v-else-if="scope.row.deposit=='已缴纳'" style="color:#606266">已缴纳</span>
                    </template>
                </el-table-column>
                <el-table-column prop="battery" label="电池状态">
                    <template slot-scope="scope">
                        <span v-if="scope.row.battery=='报废'" style="color:#e7414d">报废</span>
                        <span v-else-if="scope.row.battery=='使用中'" style="color:#606266">使用中</span>
                        <span v-else-if="scope.row.battery=='维护中'" style="color:#606266">维护中</span>
                    </template>
                </el-table-column>
                <el-table-column prop="account" label="账号状态">
                    <template slot-scope="scope">
                        <span v-if="scope.row.account=='冻结'" style="color:#e7414d">冻结</span>
                        <span v-else-if="scope.row.account=='正常'" style="color:#606266">正常</span>
                    </template>
                </el-table-column>
                <el-table-column fixed="right" label="操作" width="160">
                    <template slot-scope="scope">
                        <el-button size="mini" @click="handleEdit(scope.$index, scope.row)" class="thaw">解冻</el-button>
                        <el-button size="mini" type="danger" @click="handleDelete(scope.$index, scope.row)">冻结
                        </el-button>
                    </template>
                </el-table-column>
            </el-table>
        </div>
        <footer>
            <el-pagination background layout="prev, pager, next" :total="100" size="10">
            </el-pagination>
        </footer>

    </div>
</template>

<script>
    export default {
        name: "customerlist",
        data() {
            return {
                input: '',
                tableData: [
                    {
                        name: '123456789',
                        date: '2019-10-10',
                        deposit: '已缴纳',
                        battery: "使用中",
                        account: "冻结"
                    },
                    {
                        name: '2345687451',
                        date: '2019-10-10',
                        deposit: '未缴纳',
                        battery: "维护中",
                        account: "正常"
                    },
                    {
                        name: '6584687451',
                        date: '2019-10-10',
                        deposit: '已缴纳',
                        battery: "报废",
                        account: "正常"
                    }
                ]
            }
        }
    };
</script>

<style>
    .el-input {
        width: 260px;
        margin: 25px 10px 40px 10px;
    }

    .customerlist .search {
        display: flex;
    }

    .customerlist .el-button--primary {
        height: 40px;
        margin-top: 25px;
    }

    .el-table .cell {
        text-align: center;
        line-height: 24px;
    }

    .el-table th {
        background-color: #d9defe;
    }

    .customerlist .el-table__fixed-right {
        height: 100vh !important;
    }

    .notnormal {
        color: #e7414d
    }

    .normal {
        color: #606266;
    }
    .customerlist{
        position: relative;
        height:600px;
        
    }
    .el-pagination {
        position: absolute;
        left: 30%;
        top: 800;
        margin-top: 200px;
    }
</style>
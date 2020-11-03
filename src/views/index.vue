<template>
    <div class="index_background">
        <div class="index_head">
            <div class="title">
                <h1>王虹景闯天涯</h1>
            </div>
            <div class="menu_body">
                <div class="menu_button" @click="loginDialog"><span>登录入口</span></div>
                <div class="menu_button" @click="tips"><span>开发中</span></div>
                <div class="menu_button" @click="tips"><span>开发中</span></div>
                <div class="menu_button" @click="tips"><span>开发中</span></div>
                <div class="menu_button" @click="tips"><span>开发中</span></div>
                <div class="menu_button" @click="tips"><span>开发中</span></div>
                <div class="menu_button" @click="tips"><span>开发中</span></div>
                <div class="menu_button" @click="tips"><span>开发中</span></div>
                <div class="menu_button" @click="tips"><span>开发中</span></div>
                <div class="menu_button" @click="tips"><span>开发中</span></div>
            </div>
        </div>
        <el-dialog
                title="提示"
                :visible.sync="dialogVisible"
                width="30%"
                :before-close="handleClose">

            <span slot="footer" class="dialog-footer">
            <el-button @click="dialogVisible = false">取 消</el-button>
            <el-button type="primary" @click="dialogVisible = false">确 定</el-button>
            </span>
        </el-dialog>
    </div>
</template>

<script>
    export default {
        name: "index",
        data() {
            return {
                dialogVisible:false
            }
        },
        methods: {
            tips() {
                alert("功能正在研发中。。。。。。")
            },
            loginDialog(){
                this.dialogVisible=true
            },
            handleClose(done) {
                this.$confirm('确认关闭？')
                    .then(_ => {
                        done();
                    })
                    .catch(_ => {});
            }
        }
    }
</script>

<style scoped>
    .index_background {
        background-image: url("../assets/backgroundImage.jpg");
        background-size: 100% 100%;
        background-repeat: no-repeat;
        width: 100%;
        height: 100vh;
    }

    .index_head {
        width: 50%;
        height: 50%;
        margin-left: 25%;
        position: relative;
        top: 25%;
    }

    .title {
        text-align: center;
    }

    .menu_body {
        width: 100%;
        height: 100%;
        float: left;
    }

    .menu_button:hover{
        background-color: blue;
        color: #ffffff;
        margin-left: 1.75rem;
        margin-top: 3.5rem;
        width: 10rem;
        height: 10rem;
        border-radius: 10%;
        float: left;
        cursor: pointer;
        text-align: center;
        line-height: 10rem;
    }

    .menu_button {
        background-color: cyan;
        color: #000;
        margin-left: 1.75rem;
        margin-top: 3.5rem;
        width: 10rem;
        height: 10rem;
        border-radius: 10%;
        float: left;
        cursor: pointer;
        text-align: center;
        line-height: 10rem;
    }
</style>
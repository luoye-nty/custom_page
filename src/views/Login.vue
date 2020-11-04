<template>
    <div>
        <input type="text" v-model="loginForm.username" placeholder="用户名"/>
        <input type="text" v-model="loginForm.password" placeholder="密码"/>
        <button @click="login">登录</button>
    </div>
</template>

<script>
    import http from '../utils/http'
    export default {
        data () {
            return {
                loginForm: {
                    username: '',
                    password: ''
                }
            };
        },
        methods: {
            login () {
                //axios.defaults.headers.common["token"] = "baced";
                http.post("/api/userInfo/login",this.loginForm).then(res=>{
                    console.log(res)
                }).catch(err=>{
                    console.error("cuowu")
                })

            }
        }
    };
</script>
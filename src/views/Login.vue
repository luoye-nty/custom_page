<template>
    <div>
        <input type="text" v-model="loginForm.username" placeholder="用户名"/>
        <input type="text" v-model="loginForm.password" placeholder="密码"/>
        <button @click="login">登录</button>
    </div>
</template>

<script>
    import axios from 'axios';
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
                axios.defaults.headers.common["token"] = "baced";
                axios.post("/api/userInfo/login",this.loginForm).then(response=>(
                    console.log(response)
                ))
            }
        }
    };
</script>
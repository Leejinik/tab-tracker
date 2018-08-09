<template>
    <div>
        <h1>Register</h1>

        <input 
        type="email"
        name="email"
        v-model="email"
        placeholder="이메일"/><br>
        
        <input 
        type="password"
        name="password"
        v-model="password"
        placeholder="비밀번호"/><br>
        <!-- v-model의 password가 data().password 를 불러와 부착-->
        <!-- 그후 mouted()에서 setTimeout 2초후 hahaha 를 부착 -->
        <button
        @click ="register">
        Register
        </button>
    </div>
</template>

<script>
import AuthenticationService from '@/services/AuthenticationService'
export default {
    data(){
        return{
            email : 'chopeoghk@common.let',
            password : 'mrlee'
        }
    },
    methods:{
        async register(){
            const response = await AuthenticationService.register({
                email : this.email,
                password : this.password
            })
            console.log(response.data);
            // console.log('register button was clicked', this.email, this.password)
        }
    },
    // watch:{
    //     email(value){
    //         console.log('email has changed', value);
    //     },
    //     password(value){
    //         console.log('password has changed', value);
    //     }
    // },
    // mounted(){
    //     setTimeout(() => {
    //         this.email = 'helloworld'
    //         this.password = 'hahaha'
    //     }, 2000)
    // }
}
</script>

<style>

</style>

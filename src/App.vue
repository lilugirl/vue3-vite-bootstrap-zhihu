<script lang="ts" setup>
import 'bootstrap/dist/css/bootstrap.min.css'
import ColumnList, { ColumnProps } from './components/ColumnList.vue'
import Header from './components/GlobalHeader.vue'
import ValidateInput,{RulesProp} from './components/ValidateInput.vue'
import { reactive} from 'vue'
const testData:ColumnProps[]=[{
  id:1,
  title:'test1的专栏',
  description:'这是test1专栏，有一段非常有意思的简介，可以更新一下哦',
  avatar:'https://jira-frontend-static.prod.public.atl-paas.net/assets/permission-error.c932893e3cfcbf2f521d55c8596010e7.8.svg'
},{
  id:2,
  title:'test2的专栏',
  description:'这是test2专栏，有一段非常有意思的简介，可以更新一下哦',
  avatar:'https://jira-frontend-static.prod.public.atl-paas.net/assets/permission-error.c932893e3cfcbf2f521d55c8596010e7.8.svg'
},{
  id:3,
  title:'test3的专栏',
  description:'这是test3专栏，有一段非常有意思的简介，可以更新一下哦',
  avatar:'https://jira-frontend-static.prod.public.atl-paas.net/assets/permission-error.c932893e3cfcbf2f521d55c8596010e7.8.svg'
},{
  id:4,
  title:'test4的专栏',
  description:'这是test4专栏，有一段非常有意思的简介，可以更新一下哦'
 // avatar:'https://jira-frontend-static.prod.public.atl-paas.net/assets/permission-error.c932893e3cfcbf2f521d55c8596010e7.8.svg'
},{
  id:5,
  title:'test5的专栏',
  description:'这是test5专栏，有一段非常有意思的简介，可以更新一下哦',
  avatar:'https://jira-frontend-static.prod.public.atl-paas.net/assets/permission-error.c932893e3cfcbf2f521d55c8596010e7.8.svg'
}]

const user = { isLogin: true, name: 'liuyi' }

const emailRules: RulesProp = [{
  type:'required',message:'电子邮箱地址不能为空'
},{type:'email',message:'请输入正确的电子邮箱格式'}]



</script>

<template>
 
  <div class="container">
     <Header :user="user" />
    <!-- <ColumnList :list="testData" /> -->
    <form action="">
      <div class="mb-3">
        <label class="form-label">邮箱地址</label>
        <validate-input :rules="emailRules"></validate-input>
      </div>
       <div class="mb-3">
         <label for="exampleInputPassword1" class="form-lbal">密码</label>
         <input type="password" class="form-control" id="exampleInpuPassword1" />
       </div>
    </form>
  </div>
</template>

<style scoped>

</style>

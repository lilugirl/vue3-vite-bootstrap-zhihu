
<template>
  <nav class="navbar navbar-dark bg-primary justify-content-between mb-4 px-4">
     <a class="navbar-brand" href="#"> 者也专栏</a>
     <ul v-if="!user.isLogin" class="list-inline mb-0">
       <li class="list-inline-item"><a href="#" class="btn btn-outline-light my-2">登录</a></li>
        <li class="list-inline-item"><a href="#" class="btn btn-outline-light my-2">注册</a></li>
     </ul>
      <ul v-else="user.isLogin" class="list-inline mb-0">
        <li class="list-inline-item">
          <Dropdown :title="`你好 ${user.name}`" >
            <DropdownItem>
              <a href="#" class="dropdown-item">新建文章</a>
            </DropdownItem>
             <DropdownItem disabled>
              <a href="#" class="dropdown-item">编辑资料</a>
            </DropdownItem>
             <DropdownItem>
              <a href="#" class="dropdown-item">退出登录</a>
            </DropdownItem>
          </Dropdown>
        </li>     
     </ul>
  </nav>
</template>
<script lang="ts">
import Dropdown from './Dropdown.vue'
import DropdownItem from './DropdownItem.vue'
import { PropType } from 'vue'
export interface UserProps{
  isLogin: boolean;
  name?: string;
  id?:number
}

export default {
  props: {
    user: {
      type: Object as PropType<UserProps>,
      required:true
    }
  },
  components: {
    Dropdown,
    DropdownItem
  }
}
</script>
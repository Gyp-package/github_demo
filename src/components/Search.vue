<template>
  <div>
    <section class="jumbotron">
      <h3 class="jumbotron-heading">Search Github Users</h3>
      <div>
        <input type="text" placeholder="enter the name you search" v-model="keyWord"/>
        &nbsp;
        <button @click="searchUsers">Search</button>
      </div>
    </section>
  </div>
</template>

<script>

import axios from 'axios'

export default {
  name:'Search-',
  data(){
    return{
      keyWord:'',
    }
  },
  methods:{
    searchUsers(){
      // 使用全局事件总线,事件触发
      this.$bus.$emit('updateListData',{idLoading:true,errmsg:'',users:[],isFirst:false})
      // github提供接口搜索  https://api.github.com/search/users?q=${this.keyword}
      axios.get(`https://api.github.com/search/users?q=${this.keyword}`).then(
        response=>{
          console.log('请求成功');
          this.$bus.$emit('updateListData',{idLoading:false,errmsg:'',users:response.data.items })
        },
        error=>{
          console.log('请求失败',{ idLoading:false,errmsg:error.massage ,users:[ ]});
        },
      )
    }
  }

}
</script>

<style>

</style>
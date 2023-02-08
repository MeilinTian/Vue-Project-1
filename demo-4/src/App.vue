<template>
  <div>
    <MyHeader 
      title="MyTabBar案例" 
      :background="'blue'" 
      :fontColor="'white'">
    </MyHeader>
    
    <div class="main">
      <component :is="comName"></component>
    </div>

    <MyTabBar :arr="tabList" @changeCom="changeComFn"></MyTabBar>
  </div>
</template>

<script>
import MyHeader from './components/MyHeader'
import MyTabBar from './components/MyTabBar'

import MyGoodsList from './views/MyGoodsList'
import MyGoodsSearch from './views/MyGoodsSearch'
import MyUserInfo from './views/MyUserInfo'

export default {
  components: {
    MyHeader,
    MyTabBar,
    MyGoodsList,
    MyGoodsSearch,
    MyUserInfo
  },
  data() {
    return {
      tabList: [
          {
              iconText: "icon-shangpinliebiao",
              text: "商品列表",
              componentName: "MyGoodsList"
          },
          {
              iconText: "icon-sousuo",
              text: "商品搜索",
              componentName: "MyGoodsSearch"
          },
          {
              iconText: "icon-user",
              text: "我的信息",
              componentName: "MyUserInfo"
          }
      ],
      comName: 'MyGoodsList'
    }
  },
  methods: {
    changeComFn(cName) {
      this.comName = cName;
    }
  }
}
</script>

<style scoped>
.main {
  padding-top: 45px;
  padding-bottom: 50px;
}
</style>
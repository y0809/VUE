<template>
  <div container-home>
    <mt-swipe :auto="4000">
      <mt-swipe-item v-for="item in lunbotuList" :key="item.id"><img :src="item.img" alt=""></mt-swipe-item>

    </mt-swipe>
    <!-- 九宫格 -->
    <ul class="mui-table-view mui-grid-view mui-grid-9">
      <li class="mui-table-view-cell mui-media mui-col-xs-4">
        <a href="#">
          <img src="../../images/menu1(1).png" alt="">
          <div class="mui-media-body">新闻资讯</div>
        </a>
      </li>
      <li class="mui-table-view-cell mui-media mui-col-xs-4">
        <a href="#">
          <img src="../../images/menu2.png" alt="">
          <div class="mui-media-body">图片分享</div>
        </a>
      </li>
      <li class="mui-table-view-cell mui-media mui-col-xs-4">
        <a href="#">
          <img src="../../images/menu3.png" alt="">
          <div class="mui-media-body">商品购买</div>
        </a>
      </li>
      <li class="mui-table-view-cell mui-media mui-col-xs-4">
        <a href="#">
          <img src="../../images/menu4.png" alt="">
          <div class="mui-media-body">留言反馈</div>
        </a>
      </li>
      <li class="mui-table-view-cell mui-media mui-col-xs-4">
        <a href="#">
          <img src="../../images/menu5.png" alt="">
          <div class="mui-media-body">视频专区</div>
        </a>
      </li>
      <li class="mui-table-view-cell mui-media mui-col-xs-4">
        <a href="#">
          <img src="../../images/menu6.png" alt="">
          <div class="mui-media-body">联系我们</div>
        </a>
      </li>
    </ul>
  </div>
</template>
<script>
export default {
    data() {
        return {
            lunbotuList :null
        }
    },
    created() {
        this.getlunbotu()
    },
    methods: {
        getlunbotu() {
            this.$http.get("http://www.liulongbin.top:3005/api/getlunbo")
            .then(res=>{
                if(res.body.status ===0) {
                    this.lunbotuList = res.body.message
                } else {
                    //失败
                }
            })
        }
    }
};
</script>
<style scoped>
.mint-swipe {
  height: 200px;
}
.mint-swipe-items-wrap img{
    width: 100%;
    height: 100%;
}
.mui-table-view {
    background-color: #fff;
}
.mui-table-view img{
    width: 60px;
    height: 60px;
}
.mui-table-view .mui-table-view-cell {
    border: 0;
}
</style>



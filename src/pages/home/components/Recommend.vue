<template>
  <div>
    <div class="tittle">热销推荐</div>
    <ul>
      <router-link tag="li" :to="'/detail/'+ item.id" v-for="item of recommend" :key="item.id" class="recommend-li">
        <div class="recommend-img">
          <img :src="item.imgUrl" class="img">
        </div>
        <div class="recommend-intro">
          <p class="recommend-tittle">{{item.title}}</p>
          <p class="recommend-text">{{item.desc}}</p>
          <button class="recommend-button">查看详情</button>
        </div>
      </router-link>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  props: {
    recommend: Array
  }
}
</script>

<style lang="stylus" scoped>
  @import '~@/assets/styles/varstylus.styl'
  .tittle{
    margin-top: .2rem;
    line-height: .8rem;
    background: #eee;
    text-indent: .2rem;
  }
  .recommend-li{
    overflow: hidden;
    display: flex;
    height: 1.9rem;
    border-bottom: .02rem solid grey;
    .recommend-img{
      width: 1.7rem;
      height: 1.7rem;
      padding: .1rem;
      .img{
        width: 100%;
      }
    }
    .recommend-intro{
      flex: 1;
      padding: .1rem;
      min-width: 0;
      .recommend-tittle{
        line-height: .54rem;
        font-size: .32rem;
        ellipsis();
      }
      .recommend-text{
        line-height: .4rem;
        color: #ccc;
        ellipsis();
      }
      .recommend-button{
        line-height: .44rem;
        margin-top: .16rem;
        background: #ff9300
        padding: 0 .2rem;
        border-radius: .06rem;
        color: #fff;
      }
    }
  }
</style>

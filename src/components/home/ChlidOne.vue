<template>
  <div style="width:1140px;">
    <div class="flex-j-sb padd-tobos">
      <div class="d-flex">
        <img src="https://static.shiyanlou.com/frontend/dist/img/9f43b00.svg" alt="实验楼" width="130" />
        <div class="fz-sb flex-a-c">做实验，学编程</div>
      </div>
      <div class="flex-a-c">
        <div class="huise">
          <span class="padd-r hoverlv">企业版</span>
          <span>|</span>
          <span class="padd-l hoverlv">学校版</span>
        </div>
        <div class="padd-lrss denglu">登录</div>
        <div class="padd-lrss zhuce flex-a-c hoverlv">注册</div>
      </div>
    </div>
    <div class="d-flex">
      <div class="img flex-a-c">
        <img src="./666.jpg" alt width="20" height="16" class="mr-f hover"/>
        <span class="yanse hover">全部课程</span>
      </div>
      <div class="one-item padd-lr flex-j-sb">
        <div class="d-flex">
          <div class="padd-lre flex-a-c hoverlv">路径</div>
          <div class="padd-lre flex-a-c hoverlv">训练营</div>
          <div class="padd-lre flex-a-c hoverlv">楼+</div>
          <div class="padd-lre flex-a-c hoverlv">
            会员
            <img
              src="https://static.shiyanlou.com/frontend/dist/img/02a4001.svg"
              alt="hot"
              class="tag"
            />
          </div>
          <div class="flex-a-c ccc">
            <div class="padd-lre hoverlv">
            社区
            <i class="iconfont icon-xiajiantou"></i>
            </div>
            <div class="shequ padd-tobo">
              <div class="beij">讨论</div>
              <div class="beij">教程库</div>
              <div class="beij">直播</div>
              <div class="beij">比赛</div>
            </div>
          </div>
         
        </div>
        <div class="flex-a-c">
          <input type="text" placeholder="搜索 课程/问答" class="int flex-a-c" />
          <i class="iconfont icon-sousuo"></i>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "",
  props: {},
  data() {
    return {};
  },
  components: {},
  methods: {},
  mounted() {},
  watch: {},
  computed: {}
};
</script>

<style scoped lang='scss'>
.zhuce {
  height: 53px;
  background: rgb(8, 191, 145);
  color: white;
}
.huise {
  color: #999;
}
.denglu {
  color: rgb(8, 191, 145);
}
.denglu:hover {
  cursor: pointer;
  color: rgb(5, 118, 89);
}
.img {
  padding: 20px;
  background: rgb(8, 191, 145);
  width: 226px;
}
.one-item {
  background: white;
  height: 60.8px;
  width: 880px;
}
input {
  height: 31px;
  border-radius: 5px;
  border: 1px solid #999;
  color: #666;
  width: 200px;
  height: 31px;
  padding-left: 5px;
}
.int:focus {
  outline: none;
  border: 1px solid rgb(8, 191, 145);
}
.icon-sousuo {
  position: relative;
  right: 25px;
}
.tag {
  position: absolute;
  top: 80px;
  left: 747px;
}
.beij {
  padding: 15px 0 15px 15px;
}
.beij:hover {
  cursor: pointer;
  background: rgb(249,249,249);
  color: rgb(5, 118, 89);
}
</style>
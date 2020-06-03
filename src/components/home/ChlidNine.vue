<template>
  <div class="box3">
    <div class="flex-j-sb flex-a-c marg-tbsss">
      <div class="flex-a-c">
        <span class="nine-item hover">训练营强化</span>
        <span class="nine-item padd-lr">|</span>
        <span class="nine-item1 hover">专注实战的完整项目，在实战中融会贯通</span>
      </div>
      <div class="nine-item1 hover">更多></div>
    </div>
    <div v-for="(item,index) in arr" :key="index">
      <div class="nine-item2 hover">
        <img :src="item.picture_url" alt height="250" class="padd-rsw" />
        <div class="nine-item3">
          <p class="nine-item4">{{item.name}}</p>
          <p class="nine-item5">{{item.description}}</p>
          <div class="nine-item6">
            <div class="nine-item7">
              <div v-for="(item1,index1) in item.tags" :key="index1">
                <span class="marg-ris">{{item1}}</span>
              </div>
            </div>
            <span class="nine-item8">查看详情</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "",
  props: {},
  data() {
    return {
      arr: []
    };
  },
  components: {},
  methods: {
    getData() {
      axios
        .get(`http://120.78.14.107/api/v2/index/bootcamps`)
        .then(res => {
          this.arr = res.data;
        })
        .catch(err => {});
    }
  },
  mounted() {
    this.getData();
  },
  watch: {},
  computed: {}
};
</script>

<style scoped lang='scss'>
.nine-item {
  font-weight: 500;
  font-size: 24px;
  color: #565656;
}
.nine-item1 {
  font-size: 14px;
  color: #666;
}
.nine-item2 {
  background: white;
  margin-bottom: 10px;
  height: 250px;
  display: flex;
}
.nine-item3 {
  padding: 20px;
}
.nine-item4 {
  color: #424242;
  font-weight: 400;
  font-size: 16px;
  margin-bottom: 8px;
}
.nine-item5 {
  height: 103px;
  font-size: 14px;
  color: #666;
  overflow: hidden;
  word-break: break-all;
  text-overflow: ellipsis;
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-line-clamp: 5;
  margin-top: 18px;
}
.nine-item6 {
  margin-top: 30px;
  text-align: bottom;
  display: flex;
  justify-content: space-between;
}
.nine-item7 {
  display: flex;
}
.nine-item8 {
  float: right;
  padding: 4px 16px;
  margin-right: 20px;
  color: #fff !important;
  background: #ff9717;
  font-size: 21px;
}
.marg-ris {
  padding-top: 10px;
}
</style>
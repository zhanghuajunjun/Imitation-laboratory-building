<template>
  <div class="pos-res">
    <div class="pos">
      <div class="pos-ab lll">
        <div class="padd-lre " v-for="(item,index) in arr" :key="index">
          <div class="yanse bor flex-a-c fz-ss">
            <div class="marg-ris hoverlv">{{item.name}}</div>
            <div class="marg-ris hoverlv">{{item.tags[0].name}}</div>
            <div class="marg-ris hoverlv">{{item.tags[1].name}}</div>
          </div>
          <div
            class="two-item2 pos-ab bord"
            :style="{ top: index > 3 ? ((57 * (index-4))-0)+'px' : '0px'}"
          >
            <span class="two-item1 padd-lr marg-les">{{item.name}}</span>
            <div class="d-flex f-f-warp marg-tbs">
              <div v-for="(item,index) in item.tags" :key="index" class="d-flex">
                <div class="paddten">|</div>
                <div class="padd-tobos fz-ss hoverlv">{{item.name}}</div>
              </div>
              <div class="paddten">|</div>
            </div>
            <span class="two-item1 padd-lr marg-les">课程推荐</span>
            <div class="marg-tbs">
              <div v-for="(item,index) in item.recommend_courses" :key="index">
                <div class="fz-ss marg-tops marg-les hoverlv">{{item.name}}</div>
              </div>
            </div>
          </div>
        </div>
        <div class="f-dir-mid hei">
          <div class="yanse f-dir-mid two-item">经管专区</div>
        </div>
      </div>
      <div>
        <swiper ref="mySwiper" :options="swiperOptions">
          <swiper-slide v-for="(item,index) in arr1" :key="index">
            <div class="lunbo" :style="{background:item.background_color}">
              <img class=" hover" :src="item.picture_url" alt />
            </div>
          </swiper-slide>
          <div class="swiper-pagination" slot="pagination"></div>
        </swiper>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "../../../node_modules/axios/dist/axios";
import { Swiper, SwiperSlide, directive } from "vue-awesome-swiper";
import "swiper/css/swiper.css";

export default {
  name: "",
  props: {},
  data() {
    return {
      arr: [],
      arr1: [],
      swiperOptions: {
        pagination: {
          el: ".swiper-pagination"
        },
        autoplay: true
      }
    };
  },
  components: {
    Swiper,
    SwiperSlide
  },
  methods: {
    getData() {
      axios
        .get(`http://120.78.14.107/api/v2/index/categories`)
        .then(res => {
          this.arr = res.data;
        })
        .catch(err => {});
    },
    getDatas() {
      axios
        .get(`http://120.78.14.107/api/v2/index/banner-pictures`)
        .then(res => {
          this.arr1 = res.data;
        })
        .catch(err => {});
    }
  },
  mounted() {
    this.getData();
    this.getDatas();
  },
  watch: {},
  computed: {}
};
</script>

<style scoped lang='scss'>
.bor {
  height: 57px;
  border-bottom: 1px solid #bcbcbc;
}
.lll {
  left: 189.5px;
  top: 0px;
  width: 261px;
  z-index: 99;
  background: rgba(0, 0, 0, 0.18);
}

.two-item {
  width: 100px;
  height: 30px;
  border: 1px solid white;
  border-radius: 10px;
}
.hei {
  height: 61px;
}
.padd-lre:hover {
  background: white;
}
.padd-lre:hover .bor {
  color: #000;
}
.bord {
  display: none;
}
.padd-lre:hover .bord {
  display: block;
}
.pos-res {
  position: relative;
  width: 100%;
  display: flex;
  justify-content: center;
}
.pos {
  width: 100%;
  position: relative;
}
.lunbo {
  width: 100%;
  height: 100%;
  text-align: center;
}
</style>
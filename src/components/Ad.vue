<template>
  <div class="layout">
    <div class="card">
      <div class="cardTitle">
        <p class="text">
          <span style="color: rgb(253, 142, 37)">免學費！</span>
          25週變身「青年T大使」！
          <br />
          還能領
          <span style="color: rgb(253, 142, 37)">10.9萬</span>實作獎勵金，立即申請GO
        </p>
      </div>
      <div class="menu">
        <div class="list">
          <div class="listBox">
            <div v-for="region in regions" :key="region.id" class="area">
              <div class="option"
              @click.prevent.stop="isActive"
              >{{region.area}}</div>
            </div>
            <!-- <div class="area">
              <div class="option"
              :class="{ 'is-active': this.active }" 
              @click.prevent.stop="isActive"
              >台中市</div>
            </div> -->
            <!-- <div class="area">
              <div class="option">彰化市</div>
            </div>
            <div class="area">
              <div class="option">台南市</div>
            </div>
            <div class="area">
              <div class="option">高雄市</div>
            </div>
            <div class="area">
              <div class="option">台東縣</div>
            </div> -->
          </div>
          <div class="hints">
            <p class="hint"> ※歡迎依照您的所在地域發展興趣，申請加入各區/類青年T大使！ </p>
            <p class="hint"> ※因申請人數眾多，未通過者恕不通知。 </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
const dummyData = {
regions: [
  {
    id: 1,
    area: "苗栗縣",
    isActive: false,
  },
  {
    id: 2,
    area: "彰化市",
    isActive: false,
  },
  {
    id: 3,
    area: "台南市",
    isActive: false,
  },
  {
    id: 4,
    area: "高雄市",
    isActive: false,
  },
  {
    id: 5,
    area: "台東縣",
    isActive: false,
  }      
]
}
export default {
data () {
  return{
    regions: [],
    active: false
  }
},
created (){
    this.fetchRestaurants()
},
methods: {
  fetchRestaurants () {
    const {
      regions
    } = dummyData
    this.regions = regions
    },

  isActive () {
    if(this.active === false) {
      this.active = true;
    } else if(this.active === true) {
      this.active = false;
    }
  }
}
}
</script>
<style scoped>
.card {
  margin: auto;
  width: 80%;
  height: 900px;
  background: #fff;
  border-top: 20px solid rgb(253, 142, 37);
  border-bottom: 20px solid rgb(253, 142, 37);
  background: #f8f7f3;
}
.cardTitle {
  margin: 0;
}
.text {
  font-size: 26px;
  font-weight: 700;
  line-height: 42px;
  color: #13191d;
  letter-spacing: 2.4px;
  padding: 0 30px;
}
.menu {
  clear: left;
  margin-top: 20px;
  height: 80%;
  width: 90%;
  margin: auto;
  margin-top: 20px;
}
.area {
  position: relative;
  margin-top: 5px;
}
.option {
  background: #f5fbff;
  font-weight: 700;
  font-size: 26px;
  line-height: 60px;
  color: #5f5f5f;
  text-align: center;
  letter-spacing: 1.8px;
}
div.option::after {
  content: "";
  position: absolute;
  top: 28px;
  left: calc(50% + 65px);
  width: 0;
  height: 0;
  border-color: #5f5f5f transparent transparent;
  border-style: solid;
  border-width: 10px 6px 0;

}
p {
  margin: 0;
}
.hints {
  font-size: 20px;
  line-height: 24px;
  color: #5f5f5f;
  text-align: justify;
}
.hint {
  padding-top: 6px;
}
.is-active {
  background: rgb(253, 142, 37);
  color: #fff;
}
.is-active::after {
border-color: #fff transparent transparent;
}
@media screen and (max-width: 359px) {
  .card {
    min-width: 288px;
  }
  .text {
    font-size: 24px;
    line-height: 30px;
    padding: 0 30px;
  }
  .menu {
    width: 90%;
  }
  .hints {
    font-size: 18px;
    line-height: 21px;
  }
}
@media screen and (max-width: 1365px) {
  .card{
    font-size: 26px;
  }
}
</style>
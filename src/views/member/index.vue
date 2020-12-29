<template>
  <div class="member">
    <div class="member_title">
      <div class="member_title_lf">成员列表</div>
      <div class="member_title_rt">
        <img src="@/assets/images/project/project_icon_search.png" alt="" />
      </div>
    </div>
    <!-- tab导航 -->
    <div class="member_nav">
      <van-tabs>
        <van-tab
          v-for="(item, index) in memberNav"
          :key="index"
          :title="item.name"
        >
        </van-tab>
      </van-tabs>
    </div>
    <!-- 标签 -->
    <div class="member_label">
      <div
        class="member_label_card"
        v-for="(item, index) in member_labelNav"
        :key="index"
      >
        <span @click.stop="onlabelopen(index)">
          <img
            class="hot"
            v-show="index == 0"
            src="@/assets/images/member/team_icon_hot.png"
            alt=""
          />
          {{ item.name }}
          <img
            v-if="index == 7 && member_labelNav.length == 8"
            src="@/assets/images/member/team_icon_open_arrow.png"
            alt=""
          />
          <img
            v-if="
              index == member_labelNav.length - 1 && member_labelNav.length > 8
            "
            src="@/assets/images/member/team_icon_retract_arrow.png"
            alt=""
          />
        </span>
      </div>
    </div>

    <!-- 列表 -->
    <div class="member_list">
    
      <div v-for="index in 8" :key="index" class="list">
        <div class="list_userinfo">
          <div class="list_userinfolf">
            <!-- 头像 -->
            <div class="user_photo">
              <img
                src="https://ss1.bdstatic.com/70cFuXSh_Q1YnxGkpoWK1HF6hhy/it/u=1885558504,498786667&fm=26&gp=0.jpg"
                alt=""
              />
              <!-- 嘉宾图标 -->
              <div class="guests_icon">
                <img src="@/assets/images/member/team_icon_guest.png" alt="" />
              </div>
            </div>
            <!-- 姓名和公司 -->
            <div class="user_info">
              <span>
                张三
                <span
                  ><img
                    src="@/assets/images/member/team_icon_wechat.png"
                    alt=""
                /></span>
              </span>
              <span>藤云安全的创始人&CEO</span>
            </div>
          </div>
          <div class="list_userinfort">
            <img src="@/assets/images/member/team_icon_position.png" alt="" />
            <span>广州</span>
          </div>
        </div>
        <div class="list_explain">
          20年以上互联网实战经验！各种行业都曾涉及过，
          累计服务用户达5亿以上！擅长：产品策划、数据
          分析、产品运营、用户引流，流量变
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        memberNav: [
          {
            name: "全部",
          },
          {
            name: "同城",
          },
          {
            name: "嘉宾",
          },
          {
            name: "分享榜",
          },
          {
            name: "分销榜",
          },
        ],
        member_labelNav: [],
        member_labelNavs: [
          {
            name: "游戏",
          },
          {
            name: "社交",
          },
          {
            name: "电订",
          },
          {
            name: "短视",
          },
          {
            name: "电商",
          },
          {
            name: "APP订阅",
          },
          {
            name: "电商阅",
          },
          {
            name: "电商阅",
          },
          {
            name: "电商电商阅",
          },
          {
            name: "电商",
          },
        ],
      };
    },
    components: {},
    watch: {},
    created() {
      let vm = this;
      let initial = vm.member_labelNavs.slice(0, 7);
      vm.memberNavfun("展开", initial);
    },
    mounted() {},
    methods: {
      // 标签展开点击
      onlabelopen(val) {
        let vm = this;
        if (val == 7) {
          vm.memberNavfun("收起", vm.member_labelNavs);
        } else {
          let initial = vm.member_labelNavs.slice(0, 7);
          vm.memberNavfun("展开", initial);
        }
      },

      // 标签展开方法抽取  name:收起，展开；arr1标签数据(后台数据)
      memberNavfun(name, arr1) {
        let vm = this;
        vm.member_labelNav = arr1;
        const _data = { name: name };
        vm.member_labelNav.push(_data);
        vm.member_labelNav = vm.unique(vm.member_labelNav);
      },

      unique(arr) {
        const res = new Map();
        return arr.filter((a) => !res.has(a.name) && res.set(a.name, 1));
      },
    },
  };
</script>

<style scoped lang="less">
  .member {
    background: @commonbg;
    min-height: calc(100vh - 98px);
    width: @width;
    padding-bottom: 100px;
    .member_title {
      height: 88px;
      font-size: 42px;
      font-weight: bold;
      color: #111111;
      box-sizing: border-box;
      padding: 0 40px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      margin-bottom: 30px;
      .member_title_rt {
        img {
          width: 36px;
          height: 36px;
        }
      }
    }

    .member_nav {
      /deep/ .van-tab--active {
        font-size: 36px;
        font-weight: bold;
        color: #333333;
      }
      /deep/ .van-tabs__nav--line {
        box-sizing: content-box;
        height: auto;
        padding-bottom: 0;
      }
      /deep/ .van-tabs--line .van-tabs__wrap {
        height: 80px;
      }
      /deep/ .van-tabs__line {
        position: absolute;
        bottom: -12px;
        left: 0;
        z-index: 1;
        width: 32px;
        height: 8px;
        background: linear-gradient(90deg, #00bbd3, #00c7b2);
        border-radius: 4px;
      }
      /deep/ .van-tab {
        position: relative;
        display: -webkit-box;
        display: -webkit-flex;
        display: -ms-flexbox;
        display: flex;
        -webkit-box-flex: 1;
        -webkit-flex: 1;
        -ms-flex: 1;
        flex: 1;
        -webkit-box-align: center;
        -webkit-align-items: center;
        -ms-flex-align: center;
        align-items: center;
        -webkit-box-pack: center;
        -webkit-justify-content: center;
        -ms-flex-pack: center;
        justify-content: center;
        box-sizing: border-box;
        padding: 0 0.10667rem;
        color: #666666;
        font-size: 30px;
        cursor: pointer;
      }
    }

    .member_label {
      width: @width;
      box-sizing: border-box;
      padding: 0 40px;
      display: flex;
      justify-content: space-between;
      // flex-wrap: wrap;
      flex-flow: row wrap;
      &::after {
        content: "";
        width: 200px;
      }
      .member_label_card {
        // width: auto;
        width: fit-content;
        width: -webkit-fit-content;
        width: -moz-fit-content;
        box-sizing: border-box;
        padding: 0 26px;
        height: 68px;
        line-height: 68px;
        background: @cardbg;
        border: 2px solid #eaeaea;
        box-shadow: 0px 4px 12px 0px rgba(0, 0, 0, 0.03);
        border-radius: 34px;
        margin-bottom: 24px;
        // margin-right: 16px;
        font-size: 28px;
        font-weight: 500;
        color: #666666;
        text-align: center;
        span {
          display: flex;
          align-items: center;
          position: relative;
          .hot {
            width: 32px;
            height: 30px;
            position: absolute;
            right: -80%;
            top: 0%;
            img {
              width: 100%;
              height: 100%;
            }
          }
          img {
            width: 18px;
            height: 20px;
            margin-left: 6px;
          }
        }
      }
    }

    .member_list {
      width: @width;
      box-sizing: border-box;
      padding: 0 40px;
      margin-top: 26px;
      .list {
        min-height: 160px;
        background: @cardbg;
        border: 2px solid #eaeaea;
        box-shadow: 0px 4px 12px 0px rgba(0, 0, 0, 0.03);
        border-radius: 24px;
        margin-bottom: 30px;

        .list_userinfo {
          width: @width;
          box-sizing: border-box;
          padding: 0px 32px 0 32px;
          display: flex;
          justify-content: space-between;
          .list_userinfolf {
            display: flex;
            .user_photo {
              width: 80px;
              height: 80px;
              border-radius: 50%;
              margin-right: 24px;
              margin-top: 32px;
              position: relative;
              .guests_icon {
                position: absolute;
                bottom: -15%;
                left: 0;
                right: 0;
                img {
                  width: 48px;
                  height: 28px;
                  margin: auto;
                }
              }
              img {
                width: 100%;
                height: 100%;
                border-radius: 50%;
              }
            }
            .user_info {
              display: flex;
              flex-direction: column;
              margin-top: 35px;
              span:nth-child(1) {
                font-size: 30px;
                font-weight: bold;
                color: #111111;
                margin-bottom: 5px;
                display: flex;
                align-items: center;
                img{
                  vertical-align: middle;
                  margin-left: 12px;
                }
              }
              span:nth-child(2) {
                font-size: 24px;
                font-weight: 500;
                color: #999999;
              }
            }
          }
          .list_userinfort {
            // margin-top: 35px;
            display: flex;
            align-items: center;

            span {
              margin-left: 10px;
              color: #999999;
              font-size: 24px;
              font-weight: 500;
            }
          }
        }
        .list_explain {
          font-size: 28px;
          padding-left: 38px;
          // padding-right:32px;
          padding-bottom: 40px;
          margin-top: 30px;
          font-weight: 500;
          color: #1a1a1a;
        }
      }
    }
  }
</style>

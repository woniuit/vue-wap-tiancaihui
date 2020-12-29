<template>
  <div class="mine">
    <div class="mine_top">
      <div class="mine_info">
        <!-- 登陆前 -->
        <div class="login_info">
          <div class="login_info_lf">
            <!-- 头像 -->
            <div class="head_portrait">
              <img
                src="@/assets/images/member/my_icon_defaultavatar_img.png"
                alt=""
              />
            </div>
            <!-- 会员信息 -->
            <div class="login_vipinfo">
              <span> 请登录 </span>
              <span>
                <img
                  src="@/assets/images/member/my_icon_redenvelopes.png"
                  alt=""
                />
                登录获得新人礼包</span
              >
            </div>
          </div>
          <div class="login_info_rt">
            <img src="@/assets/images/member/my_icon_arrow.png" alt="" />
          </div>
        </div>

        <!-- 登陆后 -->
        <div class="login_info" v-show="false">
          <div class="login_info_lf">
            <!-- 头像 -->
            <div class="head_portrait">
              <img
                src="https://ss3.bdstatic.com/70cFv8Sh_Q1YnxGkpoWK1HF6hhy/it/u=3615751978,486435029&fm=26&gp=0.jpg"
                alt=""
              />
            </div>
            <!-- 会员信息 -->
            <div class="login_vipinfo">
              <span>
                我是会员
                <img src="@/assets/images/member/my_icon_vip.png" alt="" />
              </span>
              <span>2021年12月16日到期</span>
            </div>
          </div>
          <div class="login_info_rt">
            <img src="@/assets/images/member/my_icon_arrow.png" alt="" />
          </div>
        </div>
      </div>
      <!-- 引导成为会员 -->
      <div class="induce" v-show="false">
        <div class="induce_card">
          <div class="induce_card_lf">
            <img src="@/assets/images/member/my_icon_vip.png" alt="" />
            <span>成为会员</span>
          </div>
          <div class="induce_card_rt">
            开通会员，加入天财会
            <img src="@/assets/images/member/my_icon_arrow.png" alt="" />
          </div>
        </div>
      </div>
      <!-- 主题，回帖，收藏 -->
      <div class="mine_top_tab">
        <div>
          <span>42</span>
          主题
        </div>
        <div>
          <span>42</span>
          回帖
        </div>
        <div>
          <span>42</span>
          收藏
        </div>
      </div>
    </div>

    <div class="mine_menu_first">
      <div class="menu_first" v-for="(item, index) in menu_first" :key="index">
        <div class="menu_first_lf">
          <img :src="item.icon" alt="" />
          <span>{{ item.title }}</span>
        </div>
        <div class="menu_first_rt">
          <img src="@/assets/images/mine/my_icon_arrow.png" alt="" />
        </div>
      </div>
    </div>

    <div class="mine_menu_second">
      <div
        class="menu_second"
        v-for="(item, index) in menu_second"
        :key="index"
      >
        <div class="menu_second_lf">
          <img :src="item.icon" alt="" />
          <span>{{ item.title }}</span>
        </div>
        <div class="menu_second_rt">
          <span v-show="index == 3">{{ item.rttext }}</span>
          <img src="@/assets/images/mine/my_icon_arrow.png" alt="" />
        </div>
      </div>
    </div>

    <div class="mine_menu_thirdly">
      <div
        class="menu_thirdly"
        v-for="(item, index) in menu_thirdly"
        :key="index"
      >
        <div class="menu_thirdly_lf">
          <img :src="item.icon" alt="" />
          <span>{{ item.title }}</span>
        </div>
        <div class="menu_thirdly_rt">
          <span v-show="index == 1">{{ item.rttext }}</span>
          <img src="@/assets/images/mine/my_icon_arrow.png" alt="" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  import my_icon from "@/assets/images/mine/my_icon_mess.png";
  import my_icon_more from "@/assets/images/mine/my_icon_more.png";
  import my_icon_wallet from "@/assets/images/mine/my_icon_wallet.png";
  import my_icon_invitefriends from "@/assets/images/mine/my_icon_invitefriends.png";
  import my_icon_preferences from "@/assets/images/mine/my_icon_preferences.png";
  import my_icon_improve from "@/assets/images/mine/my_icon_improve.png";
  import my_icon_service from "@/assets/images/mine/my_icon_service.png";
  import my_icon_help from "@/assets/images/mine/my_icon_help.png";
  import my_icon_setup from "@/assets/images/mine/my_icon_setup.png";
  export default {
    data() {
      return {
        menu_first: [
          {
            icon: my_icon,
            title: "我的消息",
          },
          {
            icon: my_icon_more,
            title: "更多服务",
          },
        ],
        menu_second: [
          {
            icon: my_icon_wallet,
            title: "我的钱包",
          },
          {
            icon: my_icon_invitefriends,
            title: "邀请好友",
          },
          {
            icon: my_icon_preferences,
            title: "阅读喜好",
          },
          {
            icon: my_icon_improve,
            title: "完善资料",
            rttext: "收礼物",
          },
        ],
        menu_thirdly: [
          {
            icon: my_icon_service,
            title: "加下客服",
            rttext: "已加",
          },
          {
            icon: my_icon_help,
            title: "帮助中心",
          },
          {
            icon: my_icon_setup,
            title: "设置",
          }
        ],
      };
    },
    components: {},
    watch: {},
    created() {},
    mounted() {},
    methods: {},
  };
</script>

<style scoped lang="less">
  .mine {
    background: #f7f7f7;
    min-height: calc(100vh - 98px);
    width: @width;
    padding-bottom: 100px;
    .mine_top {
      //   min-height: 376px;
      background: @commonbg;
      width: @width;
      .mine_info {
        height: 178px;
        width: @width;

        box-sizing: border-box;
        padding-left: 50px;
        padding-right: 50px;
        padding-top: 50px;
        .login_info {
          display: flex;
          justify-content: space-between;
          .login_info_lf {
            display: flex;
            .head_portrait {
              width: 128px;
              height: 128px;
              background: #ffffff;
              box-sizing: border-box;
              padding: 5px;
              border: 2px solid #e8e8e8;
              box-shadow: 0px 4px 12px 0px rgba(0, 0, 0, 0.06);
              border-radius: 50%;
              img {
                width: 100%;
                height: 100%;
                border-radius: 50%;
              }
            }
            .login_vipinfo {
              margin-left: 30px;
              display: flex;
              flex-direction: column;
              justify-content: space-around;
              span:nth-child(1) {
                font-size: 34px;
                font-weight: bold;
                color: #111111;
                display: flex;
                align-items: center;
                img {
                  margin-left: 12px;
                }
              }
              span:nth-child(2) {
                font-size: 26px;
                font-weight: 500;
                color: #567895;
                display: flex;
                align-items: center;
                img {
                  margin-right: 12px;
                }
              }
            }
          }
          .login_info_rt {
            display: flex;
            align-items: center;
          }
        }
      }
      .induce {
        box-sizing: border-box;
        padding-left: 40px;
        padding-right: 40px;
        margin-top: 35px;
        margin-bottom: 64px;
        .induce_card {
          box-sizing: border-box;
          padding: 0 30px;
          height: 88px;
          background: #fbeacd;
          border-radius: 44px;
          display: flex;
          justify-content: space-between;
          align-items: center;
          .induce_card_lf {
            display: flex;
            align-items: center;
            span {
              font-size: 30px;
              color: #a46228;
            }
            img {
              margin-right: 12px;
              width: 40px;
              height: 40px;
            }
          }
          .induce_card_rt {
            font-size: 26px;
            font-family: PingFang SC;
            font-weight: 500;
            color: #a46228;
            display: flex;
            align-items: center;
            img {
              margin-left: 10px;
              width: 12px;
              height: 18px;
              vertical-align: middle;
            }
          }
        }
      }
      .mine_top_tab {
        width: @width;
        display: flex;
        margin-top: 64px;
        padding-bottom: 64px;
        justify-content: space-around;
        div {
          width: 60px;
          font-size: 28px;
          font-family: PingFang SC;
          font-weight: 500;
          color: #7f7f7f;
          span {
            font-size: 40px;
            font-family: DIN Alternate;
            font-weight: bold;
            color: #111111;
          }
        }
      }
    }

    .mine_menu_first {
      .mine_menu_common_box();
      .menu_first {
        .mine_menu_common_box_list();
        .menu_first_lf {
          .mine_menu_common_listlf();
        }
        .menu_first_rt {
          .mine_menu_common_listrt();
        }
      }
    }
    .mine_menu_second {
      .mine_menu_common_box();
      .menu_second {
        .mine_menu_common_box_list();
        .menu_second_lf {
          .mine_menu_common_listlf();
        }
        .menu_second_rt {
          .mine_menu_common_listrt();
        }
      }
    }
    .mine_menu_thirdly {
      .mine_menu_common_box();
      .menu_thirdly {
        .mine_menu_common_box_list();
        .menu_thirdly_lf {
          .mine_menu_common_listlf();
        }
        .menu_thirdly_rt {
          .mine_menu_common_listrt();
        }
      }
    }
  }
</style>

<template>
  <div class="home">
    <div class="home_topheader">
      <div class="title">
        <div class="title_lf">
          <img src="@/assets/images/home/home_icon_logo.png" alt="" />
        </div>
        <div class="title_rt">
          <img src="@/assets/images/home/home_icon_search.png" alt="" />
          <img src="@/assets/images/home/hone_icon_share.png" alt="" />
        </div>
      </div>
      <!-- 非会员显示 -->
      <div class="home_search">
        <div class="nonmember">
          <div
            class="guests guestsphoto"
            v-for="(item, index) in 8"
            :key="index"
          ></div>
          <div class="nonmember_text">
            我要提问
            <span>
              <img src="@/assets/images/home/home_icon_arrow.png" alt="" />
            </span>
          </div>
        </div>
      </div>
      <!-- 主体内容 -->
      <div class="home_subject">
        <div class="home_tab_arrow">
          <img src="@/assets/images/home/home_icon_tab_arrow.png" alt="" />
        </div>

        <van-tabs swipeable swipe-threshold="4">
          <van-tab
            v-for="(item, index) in homeNav"
            :key="index"
            :title="item.name"
          >
            <div class="content_top">
              <div
                class="content_top_list"
                v-for="(item, index) in 3"
                :key="index"
              >
                <img src="@/assets/images/home/home_icon_topping.png" alt="" />
                <img src="@/assets/images/home/home_icon_pic.png" alt="" />
                <div>【新人必读】天财会注意事项123333333333333333333333！</div>
              </div>
            </div>

            <!-- 发布的主体内容 -->
            <div class="subject">
              <div class="subject_top">
                <img
                  src="https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=403080588,4252802564&fm=26&gp=0.jpg"
                  alt=""
                />
                <div class="user_time">
                  <div>天地</div>
                  <div>18分钟前</div>
                </div>
              </div>
              <div class="subject_text">
                <div class="text_topic">#赚钱机会</div>
                <div class="text_content" ref="detailDom">
                  看过很多写出海的文章，我觉得有些角度
                  还没写到。这篇文章其实一年前就写好了，
                  但因为时机未到，所以没有发布！看过很多写出海的文章，我觉得有些角度
                  还没写到。这篇文章其实一年前就写好了，
                  但因为时机未到，所以没有发布！
                </div>
                <div v-if="showDetailBtn" class="read_more">查看全文></div>
              </div>

              <div class="subject_picture">
                <!-- subject_picture_list:index>2,subject_picture_listactive:index==1 -->
                <div
                  class="subject_picture_list"
                  v-for="(item, index) in list"
                  :key="index"
                  @click.stop="onlook(index)"
                >
                  <img :src="item" alt="" />
                </div>
                <van-image-preview
                  v-model="show"
                  :images="list"
                  :startPosition="startPosition"
                  :showIndicators="true"
                  :showIndex="false"
                >
                </van-image-preview>
              </div>
            </div>
          </van-tab>
        </van-tabs>
      </div>
    </div>
    <!-- 发布主题 -->
    <div class="issue">
      <img src="@/assets/images/home/home_icon_publishingtopics.png" alt="" />
    </div>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        home_search: "",
        showDetailBtn: true, // 是否显示“查看全文”按钮
        homeNav: [
          {
            name: "全部主题",
          },
          {
            name: "精华主题",
          },
          {
            name: "热门主题",
          },
          {
            name: "第一桶金",
          },
          {
            name: "赚钱机会",
          },
        ],
        list: [
          "https://ss2.bdstatic.com/70cFvnSh_Q1YnxGkpoWK1HF6hhy/it/u=3080431379,2023536265&fm=26&gp=0.jpg",
          "https://ss2.bdstatic.com/70cFvnSh_Q1YnxGkpoWK1HF6hhy/it/u=3080431379,2023536265&fm=26&gp=0.jpg",
          "https://ss2.bdstatic.com/70cFvnSh_Q1YnxGkpoWK1HF6hhy/it/u=3080431379,2023536265&fm=26&gp=0.jpg",
        ],
        show: false,
        startPosition: 0,
      };
    },
    components: {},
    watch: {},
    created() {},
    mounted() {},
    methods: {
      onlook(index) {
        this.startPosition = index;
        this.show = true;
      },
    },
  };
</script>

<style scoped lang="less">
  .home {
    background: @commonbg;
    min-height: calc(100vh - 98px);
    width: @width;
    .home_topheader {
      width: @width;
      padding-top: 52px;
      box-sizing: border-box;
      background: linear-gradient(0deg, #00bbd3, #00c7b2);
      .title {
        width: @width;
        display: flex;
        justify-content: space-between;
        box-sizing: border-box;
        padding: 0 40px;
        padding-bottom: 64px;
        .title_rt {
          width: 120px;
          height: 50px;
          display: flex;
          align-items: center;
          justify-content: space-between;
          img {
            width: 36px;
            height: 36px;
          }
        }
      }
      .home_search {
        width: @width;
        padding: 0 55px;
        padding-bottom: 40px;
        .nonmember {
          height: 100px;
          background: #ffffff;
          box-shadow: 0px 8px 12px 0px rgba(0, 35, 39, 0.06);
          border-radius: 50px;
          box-sizing: border-box;
          padding: 21px 0px 21px 32px;
          display: flex;
          align-items: center;
          position: relative;

          .guests {
            width: 58px;
            height: 58px;
            background: rgb(130, 137, 238);
            border-radius: 50%;
            &:nth-child(2) {
              position: absolute;
              left: 71px;
              z-index: 1;
              background: rgb(130, 137, 238);
            }
            &:nth-child(3) {
              position: absolute;
              left: 115px;
              z-index: 2;
              background: rgb(130, 137, 238);
            }
            &:nth-child(4) {
              position: absolute;
              left: 158px;
              z-index: 3;
              background: rgb(130, 137, 238);
            }
            &:nth-child(5) {
              position: absolute;
              left: 202px;
              z-index: 4;
              background: rgb(130, 137, 238);
            }
            &:nth-child(6) {
              position: absolute;
              left: 246px;
              z-index: 5;
              background: rgb(130, 137, 238);
            }
            &:nth-child(7) {
              position: absolute;
              left: 290px;
              z-index: 6;
              background: rgb(130, 137, 238);
            }
            &:nth-child(8) {
              position: absolute;
              left: 334px;
              z-index: 7;
              background: rgb(130, 137, 238);
            }
            &:nth-child(9) {
              position: absolute;
              left: 378px;
              z-index: 8;
              background: rgb(130, 137, 238);
            }
            &:nth-child(10) {
              position: absolute;
              left: 422px;
              z-index: 9;
              background: rgb(130, 137, 238);
            }
          }

          .nonmember_text {
            font-size: 28px;
            font-weight: bold;
            color: #00bbd3;
            position: absolute;
            right: 32px;
            display: flex;
            align-items: center;
            span {
              margin-left: 10px;
            }
          }
        }
      }
      .home_subject {
        width: @width;
        background: #ffffff;
        height: 200px;
        border-radius: 20px 20px 0px 0px;
        box-sizing: border-box;
        padding: 34px 40px 48px 40px;
        position: relative;

        .home_tab_arrow {
          position: absolute;
          top: 35%;
          right: 4%;
          z-index: 1;
        }
        .content_top {
          .content_top_list {
            display: flex;
            align-items: center;
            height: 89px;
            border: 1px solid #e8e8e8ff;
            border-left: none;
            border-right: none;
            box-shadow: 0px -1px 0px 0px #e8e8e8;
            &:nth-child(2) {
              border-top: none;
            }
            &:nth-child(3) {
              border-top: none;
            }
            img {
              margin-right: 20px;
            }
            div {
              font-size: 28px;
              font-weight: 500;
              color: #333333;
              white-space: nowrap;
              overflow: hidden;
              text-overflow: ellipsis;
            }
          }
        }
        .subject {
          margin-top: 40px;
          .subject_top {
            display: flex;
            .user_time {
              display: flex;
              flex-direction: column;
              div:nth-child(1) {
                font-size: 28px;
                font-weight: 500;
                color: #557794;
                // margin-bottom: 10px;
              }
              div:nth-child(2) {
                font-size: 20px;
                font-weight: 500;
                color: #b2b2b2;
              }
            }
            img {
              margin-right: 20px;
              width: 60px;
              height: 60px;
              border-radius: 50%;
            }
          }

          .subject_text {
            margin-top: 30px;
            padding-left: 80px;
            box-sizing: border-box;
            .text_topic {
              font-size: 32px;
              font-weight: 500;
              color: #9bb2c7;
              margin-bottom: 15px;
            }
            .text_content {
              font-size: 32px;
              font-family: PingFang SC;
              font-weight: 500;
              color: #1a1a1a;
              line-height: 48px;

              overflow: hidden;
              text-overflow: ellipsis;
              display: -webkit-box;
              -webkit-line-clamp: 2;
              line-clamp: 2;
              -webkit-box-orient: vertical;
            }
            .read_more {
              font-size: 32px;
              font-weight: 500;
              color: #567895;
              margin-top: 30px;
              margin-bottom: 32px;
            }
          }

          .subject_picture {
            // align-items: center;
            padding-left: 80px;
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
            &::after {
              content: "";
              width: 188px;
            }
            .subject_picture_list {
              width: 188px;
              height: 188px;
              margin-bottom: 8px;
              img {
                width: 100%;
                height: 100%;
              }
            }
            .subject_picture_listactive {
              min-width: 188px;
              min-height: 188px;
              margin-bottom: 8px;
              img {
                width: 100%;
                height: 100%;
              }
            }
          }
        }
        /deep/ .van-tabs__line {
          position: absolute;
          bottom: 40px;
          left: 0;
          z-index: 1;
          width: 32px;
          height: 8px;
          background: linear-gradient(90deg, #00bbd3, #00c7b2);
          border-radius: 4px;
        }
        /deep/ .van-tab {
          color: #abacad;
          font-size: 28px;
        }
        /deep/ .van-tab--active {
          color: #333333;
          font-size: 32px;
          font-weight: bold;
        }
        /deep/ .van-tabs__nav--complete {
          padding-right: 0;
          padding-left: 0;
        }
        /deep/ .van-tabs__content {
          padding-bottom: 100px;
        }
      }
    }
    .issue {
      position: fixed;
      right: 40px;
      bottom: 130px;
      border-radius: 50%;
    }
  }
</style>

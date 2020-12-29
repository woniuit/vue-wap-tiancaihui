<template>
  <div class="project">
    <div class="project_title">
      <div class="project_title_lf">项目大盘</div>
      <div class="project_title_rt">
        <img src="@/assets/images/project/project_icon_search.png" alt="" />
        <img src="@/assets/images/project/project_icon_share.png" alt="" />
      </div>
    </div>
    <!-- 国内项目 -->
    <div class="project_type">
      <div class="title">
        <img src="@/assets/images/project/project_icon_list.png" alt="" />
        <span>国内项目</span>
      </div>
      <div class="project_type_card">
        <div class="type_card" v-for="(item, index) in 5" :key="index">
          <!-- 圆点标识 -->
          <div class="dot" v-show="index == 0">
            <div class="identifying"></div>
          </div>
          <!-- 标题 -->
          <div class="type_card_title">淘客</div>
          <!-- 标签 -->
          <div class="type_card_label">
            <!-- ￥ 红利-->
            <div class="bonus" v-show="index == 0">
              <img
                src="@/assets/images/project/project_icon_dividend.png"
                alt=""
              />
              <span>有红利</span>
            </div>

            <!-- ///饱和期 -->
            <div class="saturation" v-show="index == 1">
              <img
                src="@/assets/images/project/project_icon_saturated.png"
                alt=""
              />
              <span>饱和期</span>
            </div>

            <!-- -> 平稳期 -->
            <div class="basing" v-show="index == 2">
              <img
                src="@/assets/images/project/project_icon_stable.png"
                alt=""
              />
              <span>平稳期</span>
            </div>
          </div>
          <!-- 月赚 -->
          <div class="month_gain">月赚1-300万</div>
        </div>
      </div>
    </div>

    <!-- 海外项目 -->
    <div class="project_type">
      <div class="title">
        <img src="@/assets/images/project/project_icon_list.png" alt="" />
        <span>海外项目</span>
      </div>
      <div class="project_type_card">
        <div class="type_card" v-for="(item, index) in 3" :key="index">
          <!-- 圆点标识 -->
          <div class="dot" v-show="index == 0">
            <div class="identifying"></div>
          </div>
          <!-- 标题 -->
          <div class="type_card_title">淘客</div>
          <!-- 标签 -->
          <div class="type_card_label">
            <!-- ￥ 红利-->
            <div class="bonus" v-show="index == 0">
              <img
                src="@/assets/images/project/project_icon_dividend.png"
                alt=""
              />
              <span>有红利</span>
            </div>

            <!-- ///饱和期 -->
            <div class="saturation" v-show="index == 1">
              <img
                src="@/assets/images/project/project_icon_saturated.png"
                alt=""
              />
              <span>饱和期</span>
            </div>

            <!-- -> 平稳期 -->
            <div class="basing" v-show="index == 2">
              <img
                src="@/assets/images/project/project_icon_stable.png"
                alt=""
              />
              <span>平稳期</span>
            </div>
          </div>
          <!-- 月赚 -->
          <div class="month_gain">月赚1-300万</div>
        </div>
      </div>
    </div>

    <!-- 其他 -->
    <div class="project_type">
      <div class="title">
        <img src="@/assets/images/project/project_icon_list.png" alt="" />
        <span>其他</span>
      </div>
      <div class="type_else">
        <div class="type_else_card" v-for="(item, index) in 7" :key="index">
          个人项目
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    data() {
      return {};
    },
    components: {},
    watch: {},
    created() {},
    mounted() {},
    methods: {},
  };
</script>

<style scoped lang="less">
  .project {
    background: @commonbg;
    min-height: calc(100vh - 98px);
    width: @width;

    .project_title {
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
      .project_title_rt {
        width: 120px;
        display: flex;
        align-items: center;
        justify-content: space-around;
        img {
          width: 36px;
          height: 36px;
        }
      }
    }

    .project_type {
      box-sizing: border-box;
      padding: 0 40px;
      margin-bottom: 40px;
      .title {
        font-size: 34px;
        font-weight: bold;
        color: #111111;
        display: flex;
        align-items: center;
        margin-bottom: 40px;
        img {
          width: 36px;
          height: 34px;
          margin-right: 16px;
        }
      }
      .project_type_card {
        display: flex;
        justify-content: space-between;
        flex-wrap: wrap;
        &::after {
          content: "";
          width: 204px;
        }
        .type_card {
          width: 204px;
          // width: 30%;
          height: 170px;
          background: @cardbg;
          border: 2px solid #eaeaea;
          box-shadow: 0px 4px 12px 0px rgba(0, 0, 0, 0.03);
          border-radius: 10px;
          margin-bottom: 30px;
          position: relative;

          .dot {
            width: @width;
            position: absolute;
            left: 22px;
            top: 22px;
            // padding: 22px 0 0 22px;
            .identifying {
              width: 14px;
              height: 14px;
              background: @navactive;
              border-radius: 50%;
            }
          }

          .type_card_title {
            font-size: 30px;
            text-align: center;
            font-weight: bold;
            color: #111111;
            margin-top: 34px;
            margin-bottom: 5px;
          }

          .type_card_label {
            font-size: 24px;
            font-weight: 500;
            img {
              margin-right: 8px;
            }
            .bonus {
              color: #e23232;
              .align_center();
            }
            .saturation {
              color: #7d46df;
              .align_center();
            }
            .basing {
              color: #379f37;
              .align_center();
            }
          }

          .month_gain {
            text-align: center;
            font-size: 22px;
            font-weight: bold;
            color: #e23232;
            margin-top: 10px;
          }
        }
      }
      .type_else {
        display: flex;
        flex-wrap: wrap;
        align-items: center;
        justify-content: space-between;
        font-size: 30px;
        font-weight: bold;
        color: #111111;
        &::after {
          content: "";
          width: 204px;
        }
        .type_else_card {
          width: 204px;
          height: 100px;
          line-height: 100px;
          text-align: center;
          background: @cardbg;
          border: 2px solid #eaeaea;
          box-shadow: 0px 4px 12px 0px rgba(0, 0, 0, 0.03);
          border-radius: 10px;
          margin-bottom: 40px;
        }
      }
    }
  }
</style>

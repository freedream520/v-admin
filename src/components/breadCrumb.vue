<template>
  <section class="content-header">
    <el-breadcrumb separator="/">
      <el-breadcrumb-item :to="{ path: '/' }">首页</el-breadcrumb-item>
      <el-breadcrumb-item v-if="rtParent!=''">{{rtParent}}</el-breadcrumb-item>
      <el-breadcrumb-item v-if="rtName!=''">{{rtName}}</el-breadcrumb-item>
    </el-breadcrumb>
  </section>
</template>
<script>
  export default {
    name: 'breadcrumb',
    data() {
      return {
      }
    },
    computed: {
      rtParent() {
        return this.$store.state.breadCrumb.rtParent;
      },
      rtName(){
          return this.$store.state.breadCrumb.rtName;
      }
    },
    methods: {

    },
    beforeRouteLeave(to,from,next){
        console.log('leave');
    }

  }
</script>
<style lang="scss" scoped>
  .content-header {
    position: relative;

    .el-breadcrumb {
      font-size: 16px;
      height: 40px;
      line-height: 40px;
    }

    > h1 {
      margin: 0;
      font-size: 24px;
      > small {
        font-size: 15px;
        display: inline-block;
        padding-left: 4px;
        font-weight: 300;
      }
    }
    .breadcrumb {
      float: right;
      background: transparent;
      margin-top: 0;
      margin-bottom: 0;
      font-size: 12px;
      /* padding:7px 5px;*/
      position: absolute;
      top: 10px;
      right: 10px;
      border-radius: 2px;
      > li {
        display: inline-block;
      }
    }
  }

  @media (max-width: 991px) {
    .content-header > .breadcrumb {
      /* position: relative;
       margin-top: 5px;
       top: 0;
       right: 0;
       float: none;
       background: #d2d6de;
       padding-left: 10px;*/
      display: none;
    }
  }

</style>

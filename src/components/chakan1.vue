<template>
<div v-if="data">
    <el-dialog  title="订单详情" :visible.sync=chakan1 :before-close="handleDialogClose" width="60%" class="qq">
      <table width="100%"  class="table" border="0">
        <tr>
          <td></td>
          <td>商品名称</td>
          <td>商品颜色</td>
          <td>商品尺码</td>
          <td>商品单价</td>
          <td>商品数量</td>
          <td>商品总价</td>
        </tr>
        <tr>
          <td class="zuo"> <img class="tu" :src=" $host+imgg" alt=""/></td>
          <td class="chu">{{this.data[0].name}}</td>
          <td class="zuo">{{this.data[0].yanSe}}</td>
          <td class="zuo">{{this.data[0].daXiao}}</td>
          <td class="zuo">{{this.data[0].danJia}}</td>
          <td class="zuo">{{this.data[0].shu}}</td>
          <td class="zuo">{{this.data[0].zongJia}}</td>
        </tr>
        <tr>
          <td class="zuo"> <img class="tu" :src=" $host+imgg" alt=""/></td>
          <td class="chu">{{this.data[1].name}}</td>
          <td class="zuo">{{this.data[1].yanSe}}</td>
          <td class="zuo">{{this.data[1].daXiao}}</td>
          <td class="zuo">{{this.data[1].danJia}}</td>
          <td class="zuo">{{this.data[1].shu}}</td>
          <td class="zuo">{{this.data[1].zongJia}}</td>
        </tr>
        <tr>
          <td></td>
          <td class="zuo"> 物流单号：</td>
          <td class="chu">{{this.data[0].wuliuhao}}</td>
          <td class="zuo">物流公司：</td>
          <td class="zuo">{{this.data[0].wuliugongsi}}</td>
          <td class="zuo">订单状态：</td>
          <td class="zuo">{{this.data[0].zhuangtai}}</td>
          <!--<td class="zuo">{{this.data[1].zongJia}}</td>-->
        </tr>
        <!--<tr>-->
          <!--<td class="zuo"> <img class="tu" :src=" $host+imgg" alt=""/></td>-->
          <!--<td class="chu">{{this.data[2].name}}</td>-->
          <!--<td class="zuo">{{this.data[2].yanSe}}</td>-->
          <!--<td class="zuo">{{this.data[2].daXiao}}</td>-->
          <!--<td class="zuo">{{this.data[2].danJia}}</td>-->
          <!--<td class="zuo">{{this.data[2].shu}}</td>-->
          <!--<td class="zuo">{{this.data[2].zongJia}}</td>-->
        <!--</tr>-->
        <!--<tr>-->
          <!--<td class="zuo"> <img class="tu" :src=" $host+imgg" alt=""/></td>-->
          <!--<td class="chu">{{this.data[3].name}}</td>-->
          <!--<td class="zuo">{{this.data[3].yanSe}}</td>-->
          <!--<td class="zuo">{{this.data[3].daXiao}}</td>-->
          <!--<td class="zuo">{{this.data[3].danJia}}</td>-->
          <!--<td class="zuo">{{this.data[3].shu}}</td>-->
          <!--<td class="zuo">{{this.data[3].zongJia}}</td>-->
        <!--</tr>-->
        <!--<tr v-for="item in data1">-->
          <!--<td class="zuo"> <img class="tu" :src=" $host+imgg" alt=""/></td>-->
          <!--<td class="chu">{{item.name}}</td>-->
          <!--<td class="zuo">{{item.yanSe}}</td>-->
          <!--<td class="zuo">{{item.daXiao}}</td>-->
          <!--<td class="zuo">{{item.danJia}}</td>-->
          <!--<td class="zuo">{{item.shu}}</td>-->
          <!--<td class="zuo">{{item.zongJia}}</td>-->
        <!--</tr>-->
      </table>
  </el-dialog>
</div>
</template>

<script>
    export default {
      name: "chakan1",
      props:['chakan1','data'],
      data() {
        return {
          form: {
            name: '',
            region: '',
            date1: '',
            date2: '',
            delivery: false,
            type: [],
            resource: '',
            desc: '',
          },
          imgg:'',
          formLabelWidth: '120px',
          data1:console.log(this.data+123)
        };
      },
      methods:{
        jianche(a){
          console.log("11111")
          console.log(a[0].img)
          this.imgg=a[0].img
          // console.log(this.imgg)
        },
        handleDialogClose(){
          console.log(this)
          this.$parent.cha1=false;
        }
      },
    };
</script>

<style scoped>
  .tu{
    /*width: 20%;*/
  }
  .qq{
    text-align: center;
  }
  .chu{
    font-weight: bold;
    /*font-size: 20px;*/
  }
  .zuo{
    /*text-align: left;*/
  }
  td{
     border-bottom-width:0px;
  }
  td{
    margin: 0;
    padding: 0;
    padding-top: 5px;
    padding-bottom: 5px;
  }
  .table{
    margin: 0;
    padding: 0;

  }
</style>

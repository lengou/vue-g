<template>
<el-container>

    <el-header>
        <el-button type="primary"  @click="dialogFormVisible = true" >添加狗狗</el-button>
         <el-autocomplete
            popper-class="my-autocomplete"
            v-model="state3"
            :fetch-suggestions="querySearch"
            placeholder="请输入内容"
            @select="handleSelect">
            <i
            class="el-icon-edit el-input__icon"
            slot="suffix"
            @click="handleIconClick">
            </i>
            <template slot-scope="{ item }">
            <div class="name">{{ item.value }}</div>
            <span class="addr">{{ item.address }}</span>
            </template>
    </el-autocomplete>
   <el-button type="primary">收索狗狗</el-button>
    
    </el-header>
    <el-main>
  <el-table
    :data="tableData5"
    style="width: 100%">
    <el-table-column type="expand">
      <template slot-scope="props">
         
        <el-form label-position="left" inline class="demo-table-expand">
          <el-form-item label="商品名称">
            <span>{{ props.row.name }}</span>
          </el-form-item>
          <el-form-item label="所属店铺">
            <span>{{ props.row.shop }}</span>
          </el-form-item>
          <el-form-item label="商品 ID">
            <span>{{ props.row.id }}</span>
          </el-form-item>
          <el-form-item label="店铺 ID">
            <span>{{ props.row.shopId }}</span>
          </el-form-item>
          <el-form-item label="商品分类">
            <span>{{ props.row.category }}</span>
          </el-form-item>
          <el-form-item label="店铺地址">
            <span>{{ props.row.address }}</span>
          </el-form-item>
          <el-form-item label="商品描述">
            <span>{{ props.row.desc }}</span>
          </el-form-item>
           <el-form-item label="修改">
            <el-button type="primary" @click="dialogFormVisible = true">修改</el-button>
             <el-button type="primary">删除</el-button>
          </el-form-item>
        </el-form>
      </template>
    </el-table-column>
    <el-table-column
      label="商品 ID"
      prop="id">
    </el-table-column>
    <el-table-column
      label="狗狗名称"
      prop="name">
    </el-table-column>
    <el-table-column
      label="狗狗性别"
      prop="sex">
    </el-table-column>
    <el-table-column
      label="狗狗颜色"
      prop="color">
    </el-table-column>
    <el-table-column
      label="狗狗描述"
      prop="desc">
    </el-table-column>
  </el-table>
  </el-main>

  <!-- 修改表格 -->
  
  <el-dialog title="修改界面" :visible.sync="dialogFormVisible">
  <el-form :model="form">
    <el-form-item label="狗狗姓名" :label-width="formLabelWidth">
       <el-col :span="10">
         <el-input  v-model="form.name" auto-complete="off"></el-input>
        </el-col>
    </el-form-item>

    <el-form-item label="狗狗姓名" :label-width="formLabelWidth">
       <el-col :span="10">
         <el-input  v-model="form.name" auto-complete="off"></el-input>
        </el-col>
    </el-form-item>
    <el-form-item label="狗狗姓名" :label-width="formLabelWidth">
       <el-col :span="10">
         <el-input  v-model="form.name" auto-complete="off"></el-input>
        </el-col>
    </el-form-item>
    <el-form-item label="狗狗姓名" :label-width="formLabelWidth">
       <el-col :span="10">
         <el-input  v-model="form.name" auto-complete="off"></el-input>
        </el-col>
    </el-form-item>
    <el-form-item label="狗狗姓名" :label-width="formLabelWidth">
       <el-col :span="10">
         <el-input  v-model="form.name" auto-complete="off"></el-input>
        </el-col>
    </el-form-item>
    <el-form-item label="狗狗姓名" :label-width="formLabelWidth">
       <el-col :span="10">
         <el-input  v-model="form.name" auto-complete="off"></el-input>
        </el-col>
    </el-form-item>
  </el-form>
  <div slot="footer" class="dialog-footer">
    <el-button @click="dialogFormVisible = false">取 消</el-button>
    <el-button type="primary" @click="dialogFormVisible = false">确 定</el-button>
    </div>
    <el-upload
  class="upload-demo"
  drag
  action="https://jsonplaceholder.typicode.com/posts/"
  multiple>
  <i class="el-icon-upload"></i>
  <div class="el-upload__text">将文件拖到此处，或<em>点击上传</em></div>
 
</el-upload>
</el-dialog>
<div class="block">
    <el-pagination
      @size-change="handleSizeChange"
      @current-change="handleCurrentChange"
      :current-page="currentPage4"
      :page-sizes="[100, 200, 300, 400]"
      :page-size="100"
      layout="total, sizes, prev, pager, next, jumper"
      :total="400">
    </el-pagination>
  </div>
      </el-container>
      
</template>

<script>
export default {
 

  data() {
    return {  tableData5: [
        {
          id: "12987122",
          name: "西瓜",
          sex: "母",
          color: "白加灰",
          category: "江浙小吃、小吃零食",
          desc: "长的好看跑的快，拆家是它大能赖",
          address: "上海市普陀区真北路",
          shop: "王小虎夫妻店",
          shopId: "10333"
        },
        {
          id: "12987123",
          name: "西瓜",
          sex: "母",
          color: "白加灰",
          category: "江浙小吃、小吃零食",
          desc: "长的好看跑的快，拆家是它大能赖",
          address: "上海市普陀区真北路",
          shop: "王小虎夫妻店",
          shopId: "10333"
        },
        {
          id: "12987125",
          name: "西瓜",
          sex: "母",
          color: "白加灰",
          category: "江浙小吃、小吃零食",
          desc: "长的好看跑的快，拆家是它大能赖",
          address: "上海市普陀区真北路",
          shop: "王小虎夫妻店",
          shopId: "10333"
        },
        {
          id: "12987126",
          name: "西瓜",
          sex: "母",
          color: "白加灰",
          category: "江浙小吃、小吃零食",
          desc: "长的好看跑的快，拆家是它大能赖",
          address: "上海市普陀区真北路",
          shop: "王小虎夫妻店",
          shopId: "10333"
        }
      ],
      restaurants: [],
      state3: "",
      dialogTableVisible: false,
      dialogFormVisible: false,
      form: {
        name: "",
        region: "",
        date1: "",
        date2: "",
        delivery: false,
        type: [],
        resource: "",
        desc: ""
      },
    
      formLabelWidth: "100px",
      currentPage1: 5,
      currentPage2: 5,
      currentPage3: 5,
      currentPage4: 4
    };
  },

  methods: {
       handleSizeChange(val) {
      console.log(`每页 ${val} 条`);
    },
    handleCurrentChange(val) {
      console.log(`当前页: ${val}`);
    },
    
    querySearch(queryString, cb) {
      var restaurants = this.restaurants;
      var results = queryString
        ? restaurants.filter(this.createFilter(queryString))
        : restaurants;
      // 调用 callback 返回建议列表的数据
      cb(results);
    },
    createFilter(queryString) {
      return restaurant => {
        return (
          restaurant.value.toLowerCase().indexOf(queryString.toLowerCase()) ===
          0
        );
      };
    },
    loadAll() {
      return [
        { value: "三全鲜食（北新泾店）", address: "长宁区新渔路144号" },
        {
          value: "Hot honey 首尔炸鸡（仙霞路）",
          address: "上海市长宁区淞虹路661号"
        },
        {
          value: "新旺角茶餐厅",
          address: "上海市普陀区真北路988号创邑金沙谷6号楼113"
        },
        { value: "泷千家(天山西路店)", address: "天山西路438号" },
        {
          value: "胖仙女纸杯蛋糕（上海凌空店）",
          address: "上海市长宁区金钟路968号1幢18号楼一层商铺18-101"
        },
        { value: "贡茶", address: "上海市长宁区金钟路633号" },
        {
          value: "豪大大香鸡排超级奶爸",
          address: "上海市嘉定区曹安公路曹安路1685号"
        },
        {
          value: "茶芝兰（奶茶，手抓饼）",
          address: "上海市普陀区同普路1435号"
        },
        { value: "十二泷町", address: "上海市北翟路1444弄81号B幢-107" },
        { value: "星移浓缩咖啡", address: "上海市嘉定区新郁路817号" },
        { value: "阿姨奶茶/豪大大", address: "嘉定区曹安路1611号" },
        { value: "新麦甜四季甜品炸鸡", address: "嘉定区曹安公路2383弄55号" },
        {
          value: "Monica摩托主题咖啡店",
          address: "嘉定区江桥镇曹安公路2409号1F，2383弄62号1F"
        },
        {
          value: "浮生若茶（凌空soho店）",
          address: "上海长宁区金钟路968号9号楼地下一层"
        },
        { value: "NONO JUICE  鲜榨果汁", address: "上海市长宁区天山西路119号" },
        { value: "CoCo都可(北新泾店）", address: "上海市长宁区仙霞西路" },
        {
          value: "快乐柠檬（神州智慧店）",
          address: "上海市长宁区天山西路567号1层R117号店铺"
        },
        {
          value: "Merci Paul cafe",
          address: "上海市普陀区光复西路丹巴路28弄6号楼819"
        },
        {
          value: "猫山王（西郊百联店）",
          address: "上海市长宁区仙霞西路88号第一层G05-F01-1-306"
        },
        { value: "枪会山", address: "上海市普陀区棕榈路" },
        { value: "阳阳麻辣烫", address: "天山西路389号" },
        {
          value: "南拳妈妈龙虾盖浇饭",
          address: "普陀区金沙江路1699号鑫乐惠美食广场A13"
        }
      ];
    },
    handleSelect(item) {
      console.log(item);
    },
    handleIconClick(ev) {
      console.log(ev);
    }
  },
  mounted() {
    this.restaurants = this.loadAll();
  }
};
</script>
<style>
.demo-table-expand {
  font-size: 0;
}
.demo-table-expand label {
  width: 90px;
  color: #99a9bf;
}
.demo-table-expand .el-form-item {
  margin-right: 0;
  margin-bottom: 0;
  width: 50%;
}
</style>
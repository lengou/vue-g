<template>
<el-container>
  <el-header>
     <el-col :span="6">
      <el-input
      placeholder="请输入内容"
      v-model="input10"
      clearable>
    </el-input>
    </el-col>
  <el-button icon="el-icon-search" circle></el-button>
   <el-button type="primary"  @click="dialogFormVisible = true" >添加商品</el-button>
    </el-header>
   <el-table
    :data="tableData"
    border
    style="width: 100%">
    <el-table-column
      fixed
      prop="date"
      label="日期"
      width="150">
    </el-table-column>
    <el-table-column
      prop="name"
      label="姓名"
      width="120">
    </el-table-column>
    <el-table-column
      prop="province"
      label="省份"
      width="120">
    </el-table-column>
    <el-table-column
      prop="city"
      label="市区"
      width="120">
    </el-table-column>
    <el-table-column
      prop="address"
      label="地址"
      width="300">
    </el-table-column>
    <el-table-column
      prop="zip"
      label="邮编"
      width="120">
    </el-table-column>
    <el-table-column
      fixed="right"
      label="操作"
      width="100">
      <template slot-scope="scope">
        <el-button @click="handleClick(scope.row)" type="text" size="small">删除该商品</el-button>
        <el-button type="text" size="small" @click="dialogFormVisible = true" >编辑修改</el-button>
      </template>
    </el-table-column>
  </el-table>

  <!-- 修改表格 -->
  
  <el-dialog title="修改界面" :visible.sync="dialogFormVisible">
  <el-form :model="form">
    <el-form-item label="商品名称" :label-width="formLabelWidth">
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
  methods: {
    handleClick(row) {
      console.log(row);
    },
     handleSizeChange(val) {
      console.log(`每页 ${val} 条`);
    },
    handleCurrentChange(val) {
      console.log(`当前页: ${val}`);
    },
  },

  data() {
    return {
      tableData: [
        {
          date: "2016-05-03",
          name: "王小虎",
          province: "上海",
          city: "普陀区",
          address: "上海市普陀区金沙江路 1518 弄",
          zip: 200333
        },
        {
          date: "2016-05-02",
          name: "王小虎",
          province: "上海",
          city: "普陀区",
          address: "上海市普陀区金沙江路 1518 弄",
          zip: 200333
        },
        {
          date: "2016-05-04",
          name: "王小虎",
          province: "上海",
          city: "普陀区",
          address: "上海市普陀区金沙江路 1518 弄",
          zip: 200333
        },
        {
          date: "2016-05-01",
          name: "王小虎",
          province: "上海",
          city: "普陀区",
          address: "上海市普陀区金沙江路 1518 弄",
          zip: 200333
        }
      ],
       input10: '',
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
  }
};
</script>
<style>
</style>
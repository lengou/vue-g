<template>


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
</el-dialog>

</template>

<script>
   export default {
    data() {
      return {
        dialogTableVisible: false,
        dialogFormVisible: false,
        form: {
          name: '',
          region: '',
          date1: '',
          date2: '',
          delivery: false,
          type: [],
          resource: '',
          desc: ''
        },
        formLabelWidth: '100px',
      };
    }
  };
</script>
<style>
    
</style>
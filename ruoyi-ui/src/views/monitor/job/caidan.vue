<template>
  <div>
    <el-row :gutter="15">
      <el-form ref="elForm" :model="formData" :rules="rules" size="medium" label-width="100px">
        <el-col :span="24">
          <el-form-item label="菜单一" prop="field102">
            <el-select v-model="formData.field102" placeholder="请选择菜单一" clearable :style="{width: '100%'}">
              <el-option v-for="(item, index) in field102Options" :key="index" :label="item.label"
                :value="item.value" :disabled="item.disabled"></el-option>
            </el-select>
          </el-form-item>
        </el-col>
        <el-col :span="24">
          <el-form-item label="菜单二" prop="field104">
            <el-select v-model="formData.field104" placeholder="请选择菜单二" clearable :style="{width: '100%'}">
              <el-option v-for="(item, index) in field104Options" :key="index" :label="item.label"
                :value="item.value" :disabled="item.disabled"></el-option>
            </el-select>
          </el-form-item>
        </el-col>
        <el-col :span="24">
          <el-form-item label="主食" prop="field105">
            <el-select v-model="formData.field105" placeholder="请选择主食" clearable :style="{width: '100%'}">
              <el-option v-for="(item, index) in field105Options" :key="index" :label="item.label"
                :value="item.value" :disabled="item.disabled"></el-option>
            </el-select>
          </el-form-item>
        </el-col>
        <el-col :span="12">
          <el-form-item label="确认" prop="field106">
            <el-button type="primary" icon="el-icon-search" size="medium"> 主要按钮 </el-button>
          </el-form-item>
        </el-col>
        <el-col :span="24">
          <el-form-item size="large">
            <el-button type="primary" @click="submitForm">提交</el-button>
            <el-button @click="resetForm">重置</el-button>
          </el-form-item>
        </el-col>
      </el-form>
    </el-row>
  </div>
</template>
<script>
export default {
  components: {},
  props: [],
  data() {
    return {
      formData: {
        field102: 1,
        field104: undefined,
        field105: undefined,
        field106: undefined,
      },
      rules: {
        field102: [{
          required: true,
          message: '请选择菜单一',
          trigger: 'change'
        }],
        field104: [{
          required: true,
          message: '请选择菜单二',
          trigger: 'change'
        }],
        field105: [{
          required: true,
          message: '请选择主食',
          trigger: 'change'
        }],
      },
      field102Options: [{
        "label": "红烧鲤鱼",
        "value": 1
      }, {
        "label": "糖醋里脊",
        "value": 2
      }, {
        "label": "红烧排骨",
        "value": ""
      }],
      field104Options: [{
        "label": "水煮白菜",
        "value": 1
      }, {
        "label": "清炒什锦",
        "value": 2
      }],
      field105Options: [{
        "label": "馒头",
        "value": 1
      }, {
        "label": "米饭",
        "value": 2
      }],
    }
  },
  computed: {},
  watch: {},
  created() {},
  mounted() {},
  methods: {
    submitForm() {
      this.$refs['elForm'].validate(valid => {
        if (!valid) return
        // TODO 提交表单
      })
    },
    resetForm() {
      this.$refs['elForm'].resetFields()
    },
  }
}

</script>
<style>
</style>

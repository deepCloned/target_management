<script setup lang="ts">

import { reactive, ref } from 'vue';
import AddTargetDialog from './add_target_dialog.vue'
const tableData = reactive([
  {
    date: '2016-05-03',
    name: 'Tom',
    address: 'No. 189, Grove St, Los Angeles',
  },
  {
    date: '2016-05-02',
    name: 'Tom',
    address: 'No. 189, Grove St, Los Angeles',
  },
  {
    date: '2016-05-04',
    name: 'Tom',
    address: 'No. 189, Grove St, Los Angeles',
  },
  {
    date: '2016-05-01',
    name: 'Tom',
    address: 'No. 189, Grove St, Los Angeles',
  },
])

function handleEdit() {}
function handleDelete() {}

const showAddTarget = ref(false)
function handleAdd() {
  showAddTarget.value = true
}

</script>

<template>
  <section class="container">
    <div class="header">
      <el-button size="small" @click="handleAdd">Add Target</el-button>
    </div>
    <div class="table-data">
      <el-table :data="tableData" style="width: 100%" border>
        <el-table-column prop="date" label="Date" width="180" />
        <el-table-column prop="name" label="Name" width="180" />
        <el-table-column prop="address" label="Address" />
        <el-table-column label="Operations">
          <template #default="scope">
            <el-button size="small" @click="handleEdit(scope.$index, scope.row)"
              >Edit</el-button
            >
            <el-button
              size="small"
              type="danger"
              @click="handleDelete(scope.$index, scope.row)"
              >Delete</el-button
            >
          </template>
        </el-table-column>
      </el-table>
    </div>
    <AddTargetDialog v-if="showAddTarget"></AddTargetDialog>
  </section>
</template>

<style scoped>
.container{
  margin-top: 50px;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.table-data{
  margin-top: 20px;
  width: 800px;
}
</style>

<script setup lang="ts">
interface Props {
  showDialog: Boolean
}

const props = withDefaults(defineProps<Props>(), {
  showDialog: false
})

</script>

<template>
  <el-dialog
    v-model="false"
    title="Tips"
    width="30%"
    :before-close="handleClose"
  >
    <span>This is a message</span>
    <template #footer>
      <span class="dialog-footer">
        <el-button @click="dialogVisible = false">Cancel</el-button>
        <el-button type="primary" @click="dialogVisible = false">
          Confirm
        </el-button>
      </span>
    </template>
  </el-dialog>
</template>
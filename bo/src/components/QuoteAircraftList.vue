<template>
  <el-table v-loading="onRemoveLoading" :data="list" style="width: 100%">
    <el-table-column type="index" min-width="20"> </el-table-column>
    <el-table-column prop="type" label="Type" min-width="180">
    </el-table-column>
    <el-table-column prop="amenities" label="Amenities" min-width="180">
    </el-table-column>
    <el-table-column v-if="!noAction" min-width="75" align="center">
      <template #default="scope">
        <el-row class="action-list">
          <el-button size="small" type="danger" @click="onRemove(scope.row)">
            <i class="icon ion-ios-trash"></i>
          </el-button>
        </el-row>
      </template>
    </el-table-column>
  </el-table>
</template>

<script>
export default {
  name: 'QuoteOptionList',
  props: {
    list: {
      type: Array,
      default: () => []
    },
    onRemove: {
      type: Function,
      default: () => {}
    },
    onRemoveLoading: {
      type: Boolean,
      default: false
    },
    noAction: {
      type: Boolean,
      default: false
    }
  }
}
</script>

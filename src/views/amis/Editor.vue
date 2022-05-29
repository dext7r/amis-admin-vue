<!-- eslint-disable -->
<template>
  <div class="editor-amis">
    <el-row class="editor-header" :gutter="20">
      <el-col :offset="1" :span="5">
        <div class="grid-content bg-purple">
          <el-link
            href="https://github.com/h7ml/vue-amis-sdk"
            style="font-size: 24px"
            target="_blank"
            >vue-amis-sdk
          </el-link>
        </div>
      </el-col>
      <el-col :offset="12" :span="6">
        <el-form ref="form" label-width="80px" :inline="true" :model="setting">
          <el-form-item>
            <el-switch
              style="display: block"
              v-model="setting.isPreview"
              active-color="#13ce66"
              inactive-color="#ff4949"
              active-text="预览"
              inactive-text="编辑"
            >
            </el-switch>
          </el-form-item>
          <el-form-item>
            <el-switch
              style="display: block"
              v-model="setting.isMobile"
              active-color="#13ce66"
              inactive-color="#ff4949"
              active-text="移动端"
              inactive-text="pc端"
            >
            </el-switch>
          </el-form-item>
        </el-form>
      </el-col>
    </el-row>
    <vue-amis-sdk
      id="editorName"
      :key="setting.updateKey"
      ref="amisEditSdk"
      :is-mobile="setting.isMobile"
      :is-preview="setting.isPreview"
      theme="cxd"
      :value="setting.schema"
      @onChange="onChange"
    />
  </div>
</template>

<script>
export default {
  name: 'Editor',
  components: {
  },
  data() {
    return {
      setting: {
        isPreview: false,
        isMobile: false,
        schema: {},
        updateKey: new Date().valueOf()
      }
    }
  },
  methods: {
    onChange(e) {
      console.log(e)
    }
  }
}
</script>
<style scoped>
.editor-amis {
}
.editor-amis > .editor-header {
  height: 40px;
}
</style>

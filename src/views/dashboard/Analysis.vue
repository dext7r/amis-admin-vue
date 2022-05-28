<template>
  <div class="Analysis">
    <div id="editor"></div>
    <div ref="renderWrap"></div>
  </div>
</template>

<script>
// @ is an alias to /src
import { Editor } from 'amis-editor'
import { setup } from 'amis-editor-sdk'
export default {
  name: 'Analysis',
  methods: {
    initEditor () {
      setup({
        id: 'editor',
        Editor,
        onChange () {},
        initSchema: this.schema // 可选
      })
    },
    // 渲染函数
    render (amisJSON) {
      if (!window.amisRequire) {
        return false
      }
      const amis = window.amisRequire('amis/embed')
      console.log(amis, this.$refs.renderWrap, amisJSON)
      amis.embed(this.$refs.renderBox, amisJSON)
    }
  },
  mounted () {
    this.initEditor()
    this.render({})
  }
}
</script>
<style>
.Analysis,#editor,.amis-editor-container,.ae-Editor{
  height: calc(100vh - 140px);
}
</style>

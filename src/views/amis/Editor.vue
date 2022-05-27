<template>
  <vue-amis-editor :is-preview="preview" :toolbar="toolbar" :value="schema" />
</template>

<script>
import VueAmisEditor from 'vue-amis-editor'
export default {
  name: 'Editor',
  components: {
    VueAmisEditor
  },
  data() {
    return {
      toolbar: {
        title: 'vue-amis-editor',
        preview: '预览',
        release: '发布',
        edit: '编辑',
        obtain: '获取',
        copy: '拷贝',
        clear: '清空',
        set: '设置'
      },
      preview: false,
      schema: {
        type: 'tasks',
        name: 'tasks',
        items: [
          {
            label: 'hive 任务',
            key: 'hive',
            status: 4,
            remark:
              '查看详情<a target="_blank" href="http://www.baidu.com">日志</a>。'
          },
          {
            label: '小流量',
            key: 'partial',
            status: 4
          },
          {
            label: '全量',
            key: 'full',
            status: 4
          }
        ],
        id: 'u:5f649ab86d6a'
      }
    }
  },
  methods: {}
}
</script>

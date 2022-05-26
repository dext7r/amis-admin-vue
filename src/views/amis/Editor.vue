<template>
  <vue-amis-editor :is-preview="preview" :value="schema" />
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

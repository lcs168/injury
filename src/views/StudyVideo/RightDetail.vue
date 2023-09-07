<template>
  <div class="main">
    <div style="height:calc(100vh - 50px);">
      <RelationGraph ref="seeksRelationGraph" :options="graphOptions" :on-node-click="onNodeClick"
                     :on-line-click="onLineClick"/>
    </div>
  </div>
</template>

<script>
import {ref} from 'vue';
import RelationGraph from 'relation-graph/vue3'

export default {
  name: "RightVideoOne",
  components: {RelationGraph},
  data() {
    return {
      graphOptions: {
        allowSwitchLineShape: true,
        allowSwitchJunctionPoint: true,
        defaultJunctionPoint: 'border',
      },
      center_: {x: -200, y: -100}, // 坐标轴起点
    }
  },
  mounted() {
    this.showSeeksGraph()
  },
  methods: {
    showSeeksGraph() {
      const __graph_json_data = {
        "rootId": "a",
        "nodes": [
          {
            "id": "0",
            "text": "0",
            "color": "orange",
            "opacity": 1,
            "disableDrag": true,
            "fixed": true,
            x: this.center_.x,
            y: this.center_.y
          },// 根节点
          {
            "id": "s1",
            "text": "s1",
            "color": "#6495ED",
            "opacity": 1,
            "disableDrag": true,
            "fixed": true,
            x: this.center_.x,
            y: this.center_.y - 300
          },// s1
          {
            "id": "s2",
            "text": "s2",
            "color": "#6495ED",
            "opacity": 1,
            "disableDrag": true,
            "fixed": true,
            x: this.center_.x + 280,
            y: this.center_.y - 180
          },// s2
          {
            "id": "s3",
            "text": "s3",
            "color": "#6495ED",
            "opacity": 1,
            "disableDrag": true,
            "fixed": true,
            x: this.center_.x + 280,
            y: this.center_.y + 180
          },// s3
          {
            "id": "s4",
            "text": "s4",
            "color": "#6495ED",
            "opacity": 1,
            "disableDrag": true,
            "fixed": true,
            x: this.center_.x,
            y: this.center_.y + 300
          },// s4
          {
            "id": "s5",
            "text": "s5",
            "color": "#6495ED",
            "opacity": 1,
            "disableDrag": true,
            "fixed": true,
            x: this.center_.x - 280,
            y: this.center_.y + 180
          },// s5
          {
            "id": "s6",
            "text": "s6",
            "color": "#6495ED",
            "opacity": 1,
            "disableDrag": true,
            "fixed": true,
            x: this.center_.x - 280,
            y: this.center_.y - 180
          },// s6
          // s1
          {
            "id": "s11",
            "text": "s11",
            "opacity": 1,
            "disableDrag": true,
            "fixed": true,
            x: this.center_.x - 150,
            y: this.center_.y - 300
          },
          {
            "id": "s12",
            "text": "s12",
            "opacity": 1,
            "disableDrag": true,
            "fixed": true,
            x: this.center_.x,
            y: this.center_.y - 450
          },
          {
            "id": "s13",
            "text": "s13",
            "opacity": 1,
            "disableDrag": true,
            "fixed": true,
            x: this.center_.x + 150,
            y: this.center_.y - 300
          },
          //s2
          {
            "id": "s21",
            "text": "s21",
            "opacity": 1,
            "disableDrag": true,
            "fixed": true,
            x: this.center_.x + 280,
            y: this.center_.y - 330
          },
          {
            "id": "s22",
            "text": "s22",
            "opacity": 1,
            "disableDrag": true,
            "fixed": true,
            x: this.center_.x + 430,
            y: this.center_.y - 180
          },
          {
            "id": "s23",
            "text": "s23",
            "opacity": 1,
            "disableDrag": true,
            "fixed": true,
            x: this.center_.x + 280,
            y: this.center_.y - 45
          },
          //s3
          {
            "id": "s31",
            "text": "s31",
            "opacity": 1,
            "disableDrag": true,
            "fixed": true,
            x: this.center_.x + 280,
            y: this.center_.y + 45
          },
          {
            "id": "s32",
            "text": "s32",
            "opacity": 1,
            "disableDrag": true,
            "fixed": true,
            x: this.center_.x + 430,
            y: this.center_.y + 180
          },
          {
            "id": "s33",
            "text": "s33",
            "opacity": 1,
            "disableDrag": true,
            "fixed": true,
            x: this.center_.x + 280,
            y: this.center_.y + 330
          },
          //s4
          {
            "id": "s41",
            "text": "s41",
            "opacity": 1,
            "disableDrag": true,
            "fixed": true,
            x: this.center_.x - 150,
            y: this.center_.y + 300
          },
          {
            "id": "s42",
            "text": "s42",
            "opacity": 1,
            "disableDrag": true,
            "fixed": true,
            x: this.center_.x,
            y: this.center_.y + 450
          },
          {
            "id": "s43",
            "text": "s43",
            "opacity": 1,
            "disableDrag": true,
            "fixed": true,
            x: this.center_.x + 150,
            y: this.center_.y + 300
          },
          //s5
          {
            "id": "s51",
            "text": "s51",
            "opacity": 1,
            "disableDrag": true,
            "fixed": true,
            x: this.center_.x - 280,
            y: this.center_.y + 45
          },
          {
            "id": "s52",
            "text": "s52",
            "opacity": 1,
            "disableDrag": true,
            "fixed": true,
            x: this.center_.x - 430,
            y: this.center_.y + 180
          },
          {
            "id": "s53",
            "text": "s53",
            "opacity": 1,
            "disableDrag": true,
            "fixed": true,
            x: this.center_.x - 280,
            y: this.center_.y + 330
          },
          //s6
          {
            "id": "s61",
            "text": "s61",
            "opacity": 1,
            "disableDrag": true,
            "fixed": true,
            x: this.center_.x - 280,
            y: this.center_.y - 330
          },
          {
            "id": "s62",
            "text": "s62",
            "opacity": 1,
            "disableDrag": true,
            "fixed": true,
            x: this.center_.x - 430,
            y: this.center_.y - 180
          },
          {
            "id": "s63",
            "text": "s63",
            "opacity": 1,
            "disableDrag": true,
            "fixed": true,
            x: this.center_.x - 280,
            y: this.center_.y - 45
          },
        ],
        "lines": [
          {"from": "0", "to": "s1"},
          {"from": "0", "to": "s2"},
          {"from": "0", "to": "s3"},
          {"from": "0", "to": "s4"},
          {"from": "0", "to": "s5"},
          {"from": "0", "to": "s6"},
          // s1
          {"from": "s1", "to": "s11"},
          {"from": "s1", "to": "s12"},
          {"from": "s1", "to": "s13"},
          // s2
          {"from": "s2", "to": "s21"},
          {"from": "s2", "to": "s22"},
          {"from": "s2", "to": "s23"},
          // s3
          {"from": "s3", "to": "s31"},
          {"from": "s3", "to": "s32"},
          {"from": "s3", "to": "s33"},
          // s4
          {"from": "s4", "to": "s41"},
          {"from": "s4", "to": "s42"},
          {"from": "s4", "to": "s43"},
          // s5
          {"from": "s5", "to": "s51"},
          {"from": "s5", "to": "s52"},
          {"from": "s5", "to": "s53"},
          // s6
          {"from": "s6", "to": "s61"},
          {"from": "s6", "to": "s62"},
          {"from": "s6", "to": "s63"},
        ]
      }
      // 以上数据中的node和link可以参考"Node节点"和"Link关系"中的参数进行配置
      this.$refs.seeksRelationGraph.setJsonData(__graph_json_data, (seeksRGGraph) => {
        // Called when the relation-graph is completed
      })
    },
    onNodeClick(node, $event) {
      console.log('选中: ', node.id, node.x, node.y)
    },
    onLineClick(lineObject, $event) {
      console.log('onLineClick:', lineObject)
    }
  }
}
</script>

<style>
.el-carousel__container {
  height: 100%;
}
</style>
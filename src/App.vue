<template>
  <div>
    <tree-view :node="treeData"></tree-view>
    <sara-tree class="item" :item="treeData"></sara-tree>
  </div>
</template>

<script>
import TreeView from "./components/TreeMenu.vue";
import SaraTree from "./components/SaraTree.vue";
//import Vue from "vue";
export default {
  name: "App",
  data() {
    return {
      treeData: [{
        name: "My Tree",
        children: [
          {
            name: "hello",
          },
          {
            name: "wat",
          },
          {
            name: "child folder",
            children: [
              {
                name: "child folder",
                children: [
                  {
                    name: "hello",
                  },
                  {
                    name: "wat",
                  },
                ],
              },
              {
                name: "hello",
              },
              {
                name: "wat",
              },
              {
                name: "child folder",
                children: [
                  {
                    name: "hello",
                  },
                  {
                    name: "wat",
                  },
                ],
              },
            ],
          },
        ],
      },
      {
        name:'sara',
        children:[
          {name:'sos'}
        ]
      }
      ],
    };
  },
  components: {
    TreeView,SaraTree
  },
  // methods: {
  //   makeFolder(item) {
  //     Vue.set(item, "children", []);
  //     // this.addItem(item);
  //   },
  // },
};
</script>

<style>
*{
  direction: rtl;
}

.item {
  cursor: pointer;
}

.bold {
  font-weight: bold;
}

ul {
  padding-left: 1em;
  line-height: 1.5em;
  list-style-type: none;
}
</style>

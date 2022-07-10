<template>
  <div>
    <li v-for="branch in item" :key="branch.id">
      <div :class="{ bold: isFolder }" @click="toggle" @dblclick="makeFolder">
        <span v-if="isFolder(branch)">{{ isOpen ? "-" : "+" }}</span> {{ branch.name }}
      </div>
      <!-- <ul v-show="isOpen" v-if="isFolder">
        <tree-item
          class="item"
          v-for="(child, index) in branch.children"
          :key="index"
          :item="child"
          @make-folder="$emit('make-folder', $event)"
          @add-item="$emit('add-item', $event)"
        ></tree-item>
      </ul> -->
    </li>
  </div>
</template>

<script>
export default {
  name: "treeItem",
  props: {
    item: Array,
  },
  data() {
    return {
      isOpen: false,
    };
  },
  computed: {
    isFolder(child) {
      // let a = this.item.forEach(element => {
      //     return element.children && element.children.length;
      // });
      // //return this.item.children && this.item.children.length;
      // return a;
      // for (let i = 0; i < this.item.length; i++) {
      //   console.log(this.item[i].children);
      // }
      // let a = i.forEach(ele => {
      //     if(ele.children && ele.children.length)  return;
      // });
      // console.log(this.item[0].children);
      // console.log(this.item[1].children);
      // console.log(this.item[2].children);
      // for(var i =0; i<this.item.length;i++){
      //    console.log(this.item[i].children&&this.item[i].children.length);
      // }
      console.log(typeof(this.item[child].children));
      //return this.item[child].children && this.item[child].children.length;
      return true;
      //return this.item.children && this.item.children.length;
    },
  },
  // methods: {
  //   toggle() {
  //     if (this.isFolder) {
  //       this.isOpen = !this.isOpen;
  //     }
  //   },
  //   makeFolder() {
  //     if (!this.isFolder) {
  //       this.$emit("make-folder", this.item);
  //       this.isOpen = true;
  //     }
  //   },
  // },
};
</script>

<style>
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
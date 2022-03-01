<!--
 * @Date: 2022-03-01 11:28:11
 * @LastEditors: zhangwen
 * @LastEditTime: 2022-03-01 12:08:25
 * @FilePath: /vue3_elementplus/src/components/common/Index.vue
-->
<template>
  <el-row class="tac">
    <el-col :span="4">
      <h5 class="mb-2">{{ title }}</h5>
      <el-menu
        :default-active="default_active"
        class="el-menu-vertical-demo"
        @open="handleOpen"
        @close="handleClose"
      >
        <el-sub-menu
          v-for="menu of menu_list"
          :index="menu.index"
          :key="menu.index"
        >
          <template #title>{{ menu.sub_menu }}</template>
          <el-menu-item
            v-for="item of menu.menu_item"
            :index="item.index"
            :key="item.index"
            >{{ item.menu_item }}</el-menu-item
          >
        </el-sub-menu>
      </el-menu>
    </el-col>
    <el-col :span="20"></el-col>
  </el-row>
</template>
<script lang="ts">
import { defineComponent, reactive, toRefs } from "vue-demi";
export default defineComponent({
  name: "Index",
  components: {},
  props: {
    name: {
      type: String,
      default: "",
    },
  },
  emits: ["success"],
  setup(props, { emit }) {
    const data = reactive({
      title: "element-plus",
      default_active: "1",
      menu_list: [
        {
          index: "Navigation",
          sub_menu: "Navigation 导航",
          menu_item: [
            {
              index: "Navigation_Menu",
              menu_item: "Menu 菜单",
            },
          ],
        },
      ],
    });
    function Init() {
      emit("success");
    }
    const handleOpen = (key: string, keyPath: string[]) => {
      console.log(key, keyPath);
    };
    const handleClose = (key: string, keyPath: string[]) => {
      console.log(key, keyPath);
    };

    return {
      ...toRefs(data),
      Init,
      handleOpen,
      handleClose,
    };
  },
});
</script>
<style scoped lang="scss"></style>

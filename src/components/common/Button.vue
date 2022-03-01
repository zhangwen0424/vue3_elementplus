<!--
 * @Date: 2022-03-01 11:06:53
 * @LastEditors: zhangwen
 * @LastEditTime: 2022-03-01 11:16:34
 * @FilePath: /vue3_elementplus/src/components/common/Button.vue
-->
<template>
  <div></div>
</template>
<script lang="ts">
import { defineComponent, reactive, toRefs } from "vue-demi";
export default defineComponent({
  name: "Button",
  components: {},
  props: {
    name: {
      type: String,
      default: "",
    },
  },
  emits: ["success"],
  setup(props, { emit }) {
    const data = reactive({});
    function Init() {
      emit("success");
    }
    return {
      ...toRefs(data),
      Init,
    };
  },
});
</script>
<style scoped lang="scss"></style>

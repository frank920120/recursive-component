<template>
  <div id="app">
    <treeBrowswer
      v-for="(list, index) in menuList"
      :roots="list"
      :key="index"
    />
  </div>
</template>

<script>
import treeBrowswer from "./components/treeBrowser";
export default {
  components: {
    treeBrowswer,
  },
  data() {
    return {
      menuList: [
        {
          title: "菜单1",
          children: [
            {
              title: "菜单1-1",
              children: [
                { title: "菜单1-1-1" },
                { title: "菜单1-1-2" },
                { title: "菜单1-1-3" },
              ],
            },
            { title: "菜单1-2" },
            { title: "菜单1-3" },
          ],
        },
        {
          title: "菜单2",
          children: [
            { title: "菜单2-1-1" },
            { title: "菜单2-1-2" },
            { title: "菜单2-1-3" },
          ],
        },
        {
          title: "菜单3",
          children: [
            { title: "菜单3-1-1" },
            { title: "菜单3-1-2" },
            { title: "菜单3-1-3" },
          ],
        },
      ],
    };
  },
};
</script>
<style></style>

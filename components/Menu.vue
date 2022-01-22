<template>
  <el-container>
    <el-aside width="200px" style="background-color: rgb(238, 241, 246)">
      <el-menu
        :default-openeds="['1', '3']"
        style="min-height: 100vh"
        :router="true"
      >
        <template v-for="menu in menus">
          <el-submenu v-if="menu.children" :key="menu.id" :index="menu.index">
            <template slot="title"
              ><i class="el-icon-message"></i>{{ menu.title }}</template
            >

            <el-menu-item
              v-for="item in menu.children"
              :key="item.index"
              :index="`${menu.index}/${item.index}`"
              >{{ item.title }}</el-menu-item
            >
          </el-submenu>

          <el-menu-item :key="menu.index" v-else :index="`${menu.index}`"
            ><i class="el-icon-message"></i>{{ menu.title }}</el-menu-item
          >
        </template>

        <!-- <el-submenu index="1">
          <template slot="title"
            ><i class="el-icon-message"></i>导航一</template
          >
          <el-menu-item-group>
            <template slot="title">分组一</template>
            <el-menu-item index="1-1">选项1</el-menu-item>
            <el-menu-item index="1-2">选项2</el-menu-item>
          </el-menu-item-group>
          <el-menu-item-group title="分组2">
            <el-menu-item index="1-3">选项3</el-menu-item>
          </el-menu-item-group>
          <el-submenu index="1-4">
            <template slot="title">选项4</template>
            <el-menu-item index="1-4-1">选项4-1</el-menu-item>
          </el-submenu>
        </el-submenu> -->
        <!-- <el-submenu index="2">
          <template slot="title"><i class="el-icon-menu"></i>导航二</template>
          <el-menu-item-group>
            <template slot="title">分组一</template>
            <el-menu-item index="2-1">选项1</el-menu-item>
            <el-menu-item index="2-2">选项2</el-menu-item>
          </el-menu-item-group>
          <el-menu-item-group title="分组2">
            <el-menu-item index="2-3">选项3</el-menu-item>
          </el-menu-item-group>
          <el-submenu index="2-4">
            <template slot="title">选项4</template>
            <el-menu-item index="2-4-1">选项4-1</el-menu-item>
          </el-submenu>
        </el-submenu> -->
      </el-menu>
    </el-aside>

    <el-container>
      <el-header style="text-align: right; font-size: 12px">
        <el-dropdown>
          <i class="el-icon-setting" style="margin-right: 15px"></i>
          <el-dropdown-menu slot="dropdown">
            <el-dropdown-item>查看</el-dropdown-item>
            <el-dropdown-item>新增</el-dropdown-item>
            <el-dropdown-item>删除</el-dropdown-item>
          </el-dropdown-menu>
        </el-dropdown>
        <span>王小虎</span>
      </el-header>

      <el-main>
        <slot></slot>
      </el-main>
    </el-container>
  </el-container>
</template>

<style>
.el-header {
  background-color: #b3c0d1;
  color: #333;
  line-height: 60px;
}

.el-aside {
  color: #333;
}

.el-menu {
}
</style>

<script>
export default {
  data() {
    const item = {
      date: "2016-05-02",
      name: "王小虎",
      address: "上海市普陀区金沙江路 1518 弄",
    };
    return {
      tableData: Array(20).fill(item),
      menus: [
        {
          index: "prototype",
          title: "原型链",
          children: [
            { index: "gzhs", title: "构造函数" },
            { index: "12", title: "辩题2" },
          ],
        },
        {
          index: "2",
          title: "标题1",
          /* children: [
            { id: 21, title: "辩题11" },
            { id: 22, title: "辩题22" },
          ], */
        },
      ],
    };
  },
};
</script>
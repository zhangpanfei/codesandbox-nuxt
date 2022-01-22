<template>
  <div>123</div>
</template>

<script>
export default {
  head: {
    title: "构造函数",
  },
  created() {
    console.log(this);
    /* function Persion(name) {
      console.log(this);
      this.name = name;
    }

    const p1 = new Persion("张三");
    Persion("李四");
    console.log(p1); */
  },
};
</script>

<template>
  <div>
    <Menu>
      <Nuxt />
    </Menu>
  </div>
</template>

<script>
import Menu from "~/components/Menu";

export default {
  components: { Menu },
  setup() {},
};
</script>

<style>
 body {
   margin: 0;
 }
</style>

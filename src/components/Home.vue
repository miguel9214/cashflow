<template>
  <div>
    <Layout>
      <template #header>
        <Header> </Header>
      </template>
      <template #resume>
        <Resume />
      </template>
      <template #movements>
        <Movements />
      </template>
    </Layout>
  </div>
</template>
<script>
import Layout from "@/components/Layout.vue";
import Header from "@/components/Header.vue";
import Movements from "@/components/Movements.vue";
import Resume from "./Resume/Index.vue";
export default {
  components: {
    Layout,
    Header,
    Resume,
    Movements,
  },
};
</script>
<style lang=""></style>

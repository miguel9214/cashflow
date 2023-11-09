<template>
  <div>
    <Layout>
      <template #header>
        <Header> </Header>
      </template>
      <template #resume>
        <Resume 
        :label="'Ahorro total'"
        :amount="amount"
        :totalAmount="250000"
        />
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

  data() {
    return {
      data() {
        return {
          amount:null,
        }
      },
    }
  },
};
</script>
<style lang=""></style>

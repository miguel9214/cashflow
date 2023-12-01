<template>
  <div>
    <Layout>
      <template #header>
        <Header> </Header>
      </template>
      <template #resume>
        <Resume
          :label="'Ahorro total'"
          :totalLabel="totalLabel"
          :amount="amount"
          :totalAmount="1000000"
        >
          <template #graphic> Graphic </template>
          <template #action> 
            <Action/> 
          </template>
        </Resume>
      </template>
      <template #movements>
        <Movements :movements="movements" />
      </template>
    </Layout>
  </div>
</template>
<script>
import Layout from "@/components/Layout.vue";
import Header from "@/components/Header.vue";
import Resume from "./Resume/Index.vue";
import Action from "./Action.vue";
import Movements from "./Movements/Index.vue";
export default {
  components: {
    Layout,
    Header,
    Resume,
    Action,
    Movements,
  },
  data() {
    return {
      amount: null,
      label: null,
      movements: [
        {
          id: 1,
          title: "Movimiento 1",
          description: "Deposito de salario",
          amount: 1000,
        },
        {
          id: 2,
          title: "Movimiento 2",
          description: "Deposito de honorarios",
          amount: 500,
        },
        {
          id: 3,
          title: "Movimiento 3",
          description: "Comida",
          amount: -100,
        },
        {
          id: 4,
          title: "Movimiento 4",
          description: "Colegiatura",
          amount: -2000,
        },
        {
          id: 5,
          title: "Movimiento 5",
          description: "Reparación equipo",
          amount: 1000,
        },
      ],
    };
  },
};
</script>
<style lang=""></style>

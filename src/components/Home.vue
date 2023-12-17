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
          :totalAmount="totalAmount"
        >
          <template #graphic>
            <Graphic :amounts="amounts" />
          </template>
          <template #action>
            <Action @create="create" />
          </template>
        </Resume>
      </template>
      <template #movements>
        <Movements :movements="movements" @remove="remove" />
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
import Graphic from "./Resume/Graphic.vue";
export default {
  components: {
    Layout,
    Header,
    Resume,
    Graphic,
    Action,
    Movements,
  },
  data() {
    return {
      amount: null,
      label: null,
      amounts: [100, 200, 500, 200, -400, -600, -300, 0, 300, 500],
      movements: [
        // {
        //   id: 1,
        //   title: "Movimiento 1",
        //   description: "Deposito de salario",
        //   amount: 100,
        //   time: new Date("14-12-2023"),
        // },
        // {
        //   id: 2,
        //   title: "Movimiento 2",
        //   description: "Deposito de honorarios",
        //   amount: 500,
        //   time: new Date("14-12-2023"),
        // },
        // {
        //   id: 3,
        //   title: "Movimiento 3",
        //   description: "Comida",
        //   amount: -100,
        //   time: new Date("14-12-2023"),
        // },
        // {
        //   id: 4,
        //   title: "Movimiento 4",
        //   description: "Colegiatura",
        //   amount: -200,
        //   time: new Date("14-12-2023"),
        // },
        // {
        //   id: 5,
        //   title: "Movimiento 5",
        //   description: "Reparación equipo",
        //   amount: 100,
        //   time: new Date("14-12-2023"),
        // },
      ],
    };
  },
  computed: {
    amounts() {
      const lastDays = this.movements
        .filter((m) => {
          const today = new Date();
          const oldDate = today.setDate(today.getDate() - 30);
          return m.time > oldDate;
        })
        .map((m) => m.amount);

      return lastDays.map((m, i) => {
        const lastMovements = lastDays.slice(0, i);

        return lastMovements.reduce((suma, movement) => {
          return suma + movement;
        }, 0);
      });
    },
    totalAmount() {
      return this.movements.reduce((suma, m) => {
        return suma + m.amount;
      }, 0);
    }
  },
  mounted() {
    const movements = JSON.parse(localStorage.getItem("movements"));
    console.log(movements);
    if (Array.isArray(movements)) {
      this.movements = movements.map(m => {
        return { ...m, time: new Date(m.time) };
      });
    }


  },

  methods: {
    create(movement) {
      this.movements.push(movement);
      this.save();
    },
    remove(id) {
      const index = this.movements.findIndex((m) => m.id === id);
      this.movements.splice(index, 1);
      this.save();
    },
    save(){
      localStorage.setItem("movements",JSON.stringify(this.movements));
    }
  },
};
</script>
<style lang=""></style>

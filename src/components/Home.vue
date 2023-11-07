<template>
    <div>
        <Layout>
            <template #header>
                <Header>

                </Header>
            </template>
            <template #resume>
                <Resume/>
       
            </template>

        </Layout>
        
    </div>
</template>
<script>
import Layout from "@/components/Layout.vue";
import Header from "@/components/Header.vue";
import Resume from "@./Resume/Index.vue";
export default {
    components:{
        Layout,
        Header,

    }
    
}
</script>
<style lang="">
    
</style>
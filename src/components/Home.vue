<template>
    <Layout>
        <template #header>
            <Header></Header>
        </template>

        <template #resume>
            <div class="resume">
                <Resume
                    :total-label="'Ahorro total'"
                    :label="label"
                    :total-amount="1000000"
                    :amount="totalAmount"
                > 
                    <template #graphic>
                        Graphic
                    </template>

                    <template #action>
                        Action
                    </template>
                </Resume>
            </div>
        </template>

        <template #movements>
            <Movements
                :movements="movement"
            />
        </template>
    </Layout>
</template>

<script>
    import Layout from "@/components/Layout.vue";
    import Header from "@/components/Header.vue";
    import Resume from "@/components/resume/Index.vue";
    import Movements from "@/components/movements/Index.vue";

    export default {
        components: {
            Layout,
            Header,
            Resume,
            Movements
        },
        data() {
            return {
                label: null,
                amount: null, 
                movement: [
                    { id: 0, title: 'Movimiento 1' , description: "Descripción del movimiento 1" , amount: 1000 },
                    { id: 1, title: 'Movimiento 2', description: "Descripción del movimiento 2", amount: 2000 },
                    { id: 2, title: 'Movimiento 3', description: "Descripción del movimiento 3", amount: 3000 },
                    { id: 3, title: 'Movimiento 4', description: "Descripción del movimiento 4", amount: 4000 },
                ],
            };
        },
    }
</script>
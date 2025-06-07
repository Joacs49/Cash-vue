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
            <Movements/>
        </template>
    </Layout>
</template>

<script>
    import Layout from "@/components/Layout.vue";
    import Header from "@/components/Header.vue";
    import Resume from "@/components/resume/Index.vue";
    import Movements from "@/components/Movements.vue";

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
            };
        },
    }
</script>
<template>
    <header>
        <img 
            @click="reload"
            src="@/assets/logo.svg" 
            alt="Logo"
        />
        <h1><span>Cash</span>Vue</h1>

        <span></span>
    </header>
</template>

<script>
    export default {
        methods: {
            reload() {
                location.reload();
            }
        }
    }
</script>

<style scoped>
    header {
        display: flex;
        align-items: center;
        justify-content: space-around;
        width: 100%;
    }

    img {
        width: 50px;
        cursor: pointer;
    }

    h1 {
        font-size: 1.4rem;
        color: var(--brand-blue);
    }

    h1 span {
        color: var(--brand-green);
    }
</style>
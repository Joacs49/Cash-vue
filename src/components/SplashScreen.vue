<template>
    <div class="splash-screen">
        <img 
            src="@/assets/logo.svg" 
            alt="Logo" 
        />

        <h1>
            <span>Cash</span>Vue
        </h1>
    </div>
</template>

<style scoped>
    .splash-screen {
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
        height: 100vh;
    }

    h1 {
        color: var(--brand-blue);
    }

    h1 span {
        color: var(--brand-green);
    }
</style>
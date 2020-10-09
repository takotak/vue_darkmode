<template>
    <div>
        <button @click="toggleTheme">Dark mode</button>
    </div>
</template>

<script>
    export default {
        methods: {
            toggleTheme() {
                document.documentElement.classList.toggle('darkmode')
            }
        }
    }
</script>

<style lang="scss">
    :root {
        --light: #fff;
        --text: #2c3e50;
        --link: #42b983;

        background: var(--light);
        transition: background-color 0.2s ease;
    }
    :root.darkmode {
        --light: #080913;
        --text: #dedede;
    }
</style>

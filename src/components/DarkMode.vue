<template>
    <div>
        <div class="mode-toggle" @click="toggleTheme">
            <h6 class="label-toggle">Dark</h6>
            <div class="toggle-switch" alt="Go dark" title="Go dark"></div>
            <h6 class="label-toggle">Light</h6>
        </div>
    </div>
</template>

<script>
    export default {
        methods: {
            toggleTheme(e) {
                document.documentElement.classList.toggle('darkmode')
                this.toggleButton(e)
            },
            toggleButton(e) {
                e.srcElement.classList.toggle('active')
            }
        }
    }
</script>

<style lang="scss">
    :root {
        --light: #FFF;
        --text: #2C3E50;
        --text-subdued: #5B5E62;
        --link: #42B983;

        background: var(--light);
        transition: background-color 0.2s ease;
    }
    :root.darkmode {
        --light: #080913;
        --text: #DEDEDE;
        --text-subdued: #B9BDC1;
    }
    .mode-toggle {
        display: inline-flex;
        align-items: center;
    }
    .label-toggle {
        text-transform: uppercase;
        padding:8px 12px;
        text-align:center;
        color: var(--text-subdued);
        margin: 0;
    }
    .toggle-switch {
        margin:0;
        padding:0;
        width:48px;
        height:28px;
        border:none;
        outline:none;
        overflow:hidden;
        position:relative;
        border-radius:14px;
        display:inline-block;
        background:#404346;

        &:before {
            top:4px;
            left:24px;
            content:"";
            width:20px;
            height:20px;
            display:block;
            position:absolute;
            border-radius:12px;
            background:#DCE0E3;
        }

        &:after {
            content:"";
            top:14px;
            right:2px;
            width:1px;
            height:1px;
            display:block;
            position:absolute;
            border-radius:0.5px;
            background:#404346;
        }

        &.active {
            background: #DCE0E3;
        }

        &.active:before {
            left:4px;
            background:#2D2F31;
        }

        &.active:after {
            top:-2px;
            right:2px;
            width:32px;
            height:32px;
            border-radius:16px;
            background:#DCE0E3;
        }
    }
    .toggle-switch,
    .toggle-switch:before,
    .toggle-switch:after {
        transition: all 0.2s ease;
    }
</style>

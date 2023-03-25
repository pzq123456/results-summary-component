<script setup>
    import RSCopnent from './components/RSCopnent.vue';
</script>

<template>
        <RSCopnent />
</template>

<style>
    :root{
        --primary-light-red: hsl(0, 100%, 67%);
        --primary-orangey-yellow: hsl(39, 100%, 56%);
        --primary-green-teal: hsl(166, 100%, 37%);
        --primary-cobalt-blue: hsl(234, 85%, 45%);

        --gradient-light-slate-blue: hsl(252, 100%, 67%);
        --gradient-light-royal-blue: hsl(241, 81%, 54%);

        --gradient-violet-blue: hsla(256, 72%, 46%, 1);
        --gradient-persian-blue: hsla(241, 72%, 46%, 0);

        --neutral-white: hsl(0, 0%, 100%);
        --neutral-pale-blue: hsl(221, 100%, 96%);
        --neutral-light-lavender: hsl(241, 100%, 89%);
        --neutral-dark-gray-blue: hsl(224, 30%, 27%);
    }

    @font-face {
        font-family: 'Hanken Grotesk';
        src: url('./assets/fonts/HankenGrotesk-VariableFont_wght.ttf') format('truetype');
        font-weight: 100 900;
        font-style: normal;
        font-display: swap;
    }

    *{
        font-family: 'Hanken Grotesk', sans-serif;

        margin: 0;
        box-sizing: border-box;
        padding: 0;
    }

    p{
        font-size: 18px;
    }

</style>



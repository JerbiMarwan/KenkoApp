<template>
    <span>
        <home-hero></home-hero>
        <!-- <home-features></home-features> -->
    </span>
</template>

<script>
import HomeHero from '@/components/HomeHero';
// import HomeFeatures from '@/components/HomeFeatures';

export default {
    name: 'home',
    components: {
        HomeHero
        // HomeFeatures
    }
};
</script>

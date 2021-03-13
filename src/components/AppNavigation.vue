<template>
    <v-toolbar color="amber" id="header" fixed>
        <v-spacer />
        <v-toolbar-title id="toolbar">
            ({{appTitle}})
        </v-toolbar-title>
        <v-spacer />
    </v-toolbar>
</template>

<script>
export default {
    name: 'AppNavigation',
    data() {
        return {
            appTitle: 'KenkoApp',
            drawer: false,
            items: [
                { title: 'Menu' },
                { title: 'Sign In' },
                { title: 'Join' }
            ]
        };
    }
};
</script>

<style scoped>
    #toolbar{
        color: white;
        font-size: 40pt;
        font-family: YellowRabbit;
        font-weight: bold;
    }
</style>
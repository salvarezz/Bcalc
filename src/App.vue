<template>
    <v-app>
        <v-main>
            <v-container fluid class="main_content">
                <Calc />
            </v-container>
        </v-main>
    </v-app>
</template>

<script>
import Calc from "./components/Calc";

export default {
    name: "App",

    components: {
        Calc,
    },

    data: () => ({
        //
    }),
};
</script>

<style>
.main_content {
    background-color: #bdbdbd;
    height: 100%;
}
</style>
<template>
    <MainMenu />
</template>

<script lang="ts">
import { defineComponent } from "vue";
import MainMenu from "./MainMenu.vue";

export default defineComponent({
    data() {
        return {
            content: "asdasd"
        };
    },
    mounted() {
        document.addEventListener("distress-alert", () => {
            this.content = "Distress Call";
        });
    },
    components: { MainMenu }
});
</script>>
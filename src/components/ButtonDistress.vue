<template>
    <button v-on:pointerdown="alarmOnLongPress()"></button>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
    methods: {
        alarmOnLongPress() {
            let timer = 0;

            document.addEventListener("pointerup", () => {
                timer = 0;
                clearInterval(interval);
            });

            const interval = setInterval(() => {
                timer++;
                if (timer >= 3) {
                    console.log("distress alert event");
                    document.dispatchEvent(new Event("distress-alert"));
                }
            }, 500);
        },
        startAlarm() {
            console.log("distress call");
        }
    },

});
</script>
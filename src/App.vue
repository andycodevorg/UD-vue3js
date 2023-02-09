<template>
    <div>
        <h1>Mi componente princiapal</h1>
        <Car :power="power" :upPower="upPower" @downPower="downPower()"/>
    </div>
</template>

<script>

import { ref } from "vue";
import Car from "./components/Car.vue";

    export default {
        components: {
            Car
        },

        setup() {
            let power = ref(1000);

            const upPower = () => {
                power.value++;
                console.log("Aumentar power desde App ...");
            }

            const downPower = () => {
                power.value--;
            }
            

            return {
                power,
                upPower,
                downPower
            }
        }
    }
</script>

<style lang="scss" scoped>

</style>
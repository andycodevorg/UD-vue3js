<template>
    <div>
        <h1>Car</h1>
        <h3>Características</h3>
        <ul>
            <li>Marca: {{ brand }}</li>
            <li>Modelo: {{ model }}</li>
        </ul>
        <h3>Potencia</h3>
        <h2>{{ power }}</h2>

        <!-- <button @click="testPower()">Aumentar Potencia</button> -->
        <button @click="upPower()">Aumentar Potencia</button>
        <button @click="downPowerFn()">Disminuir Potencia</button>
        
    </div>
</template>

<script>

export default {
    props: {
        power: {
            type: Number,
            default: 500
        },
        upPower: Function,
    },

    emits: ["downPower"],

    setup(props, context) {
        const brand = "Kia";
        const model = "Elantra";

        // console.log(context);
        // console.log(props);

        const downPowerFn = () => {
            context.emit("downPower");
        }

        // const testPower = () => {
        //     props.upPower();
        // }
     
        return {
            brand,
            model,
            downPowerFn
            // testPower
        }

    }
}
</script>

<style lang="scss" scoped>

</style>
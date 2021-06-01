<template>
    <span>
        <span v-for="filter in this.filters" :key="filter">
            <v-btn v-on:click="$emit('add-filter', filter)">{{ filter }}</v-btn>
        </span>
    </span>
</template>

<script>
export default {
    name: 'SensorList',
    components: {},
    methods: {},
    props: { filters: [Array] },
    mounted() {
        console.log(this.filters);
    },
    data() {
        return {};
    },
};
</script>

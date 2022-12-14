<template>
    <h2>{{ userName }}</h2>
    <h3>{{ uAge }}</h3>
</template>

<script>
import {
    computed,
    inject,
    onBeforeMount,
    onMounted,
    onBeforeUpdate,
    onUpdated,
    onBeforeUnmount,
    onUnmounted
} from 'vue';

export default {
    props: ['firstName', 'lastName'],
    setup(props, context) {
        // computed 
        const userName = computed(() => {
            return props.firstName + ' ' + props.lastName;
        });

        // inject
        const uAge = inject('userAge');

        console.log(context);
        // context.$emit('save-data', 1);

        // on functions
        onBeforeMount(() => {
            console.log("onBeforeMount");
        });
        onMounted(() => {
            console.log("onMounted");
        });
        onBeforeUpdate(() => {
            console.log("onBeforeUpdate");
        });
        onUpdated(() => {
            console.log("onUpdated");
        });
        onBeforeUnmount(() => {
            console.log("onBeforeUnmount");
        });
        onUnmounted(() => {
            console.log("onUnmounted");
        });

        // return props and funcs
        return {
            userName,
            uAge
        };
    }
    // computed: {
    //     userName() {
    //         return this.firstName + ' ' + this.lastName;
    //     }
    // }
};
</script>
<template>
    <h2>{{ userName }}</h2>
    <h3>{{ uAge }}</h3>
</template>

<script>
import { computed, inject } from 'vue';

export default {
    props: ['firstName', 'lastName'],
    setup(props, context) {
        const userName = computed(() => {
            return props.firstName + ' ' + props.lastName;
        });

        const uAge = inject('userAge');

        console.log(context);
        // context.$emit('save-data', 1);

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
<template>
    <h2>{{ userName }}</h2>
    <h3>{{ uAge }}</h3>
</template>

<script>
import { computed } from 'vue';

export default {
    props: ['firstName', 'lastName', 'uAge'],
    setup(props, context) {
        const userName = computed(() => {
            return props.firstName + ' ' + props.lastName;
        });

        // context.$emit('save-data', 1);

        return {
            userName
        }
    }
    // computed: {
    //     userName() {
    //         return this.firstName + ' ' + this.lastName;
    //     }
    // }
};
</script>
<template>
    <h2>{{ userName }}</h2>
    <h3>{{ uAge }}</h3>
</template>

<script>
export default {
    props: ['firstName', 'lastName', 'uAge'],
    computed: {
        userName() {
            return this.firstName + ' ' + this.lastName;
        }
    }
};
</script>